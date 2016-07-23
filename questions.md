# Các câu hỏi phỏng vấn PHP

### 1. Làm thế nào để gọi một method tĩnh từ tên class?

    `ClassName::method();`

### 2. Late static binding là gì?

    [Xem bài viết sau](https://nhaancs.wordpress.com/2016/06/09/php-oop-bai-10-late-static-bindings-tu-khoa-static/)

### 3. Sự khác nhau giữa ngăn xếp (stack) và hàng đợi (stack)?

    - Ngăn xếp (stack) sử dụng theo kiểu LIFO (last in fisrt out - vào sau ra trước): có nghĩa là dữ liệu vào sau thì sẽ được xử lý trước. Giống kiểu băng đạn.
    - Hàng đợi (stack) sử dụng theo kiểu FIFO (first in first out - vào trước ra trước): có nghĩa là dữ liệu vào trước thì sẽ được xử lý trước. Giống kiểu xếp hàng mua vé.

### 4. Truyền theo tham chiếu có nghĩa là gì?

    Truyền tham chiếu là làm biến (B) thành một alias (bí danh) của (A), lúc này (A) gần như là (B) và (B) gần như là (A) vì cả 2 đều tham chiếu đến cùng một đối tượng, mọi thay đổi trên (B) thực tế cũng là thay đổi trên (A). Từ đó, sau khi thoát ra khỏi hàm, dữ liệu trên vùng nhớ được (A) tham chiếu tới sẽ bị thay đổi theo các thao tác mà ta đã dùng để thay đổi dữ liệu trên vùng nhớ được (B) tham chiếu tới.

### 5. Transaction là gì?

    Transaction là một tiến trình xử lý có xác định điểm đầu và điểm cuối, được chia nhỏ thành các operation (phép thực thi) độc lập, tiến trình được thực thi một cách tuần tự các operation đó. Nếu việc thực thi một operation nào đó bị fail (hỏng) đồng nghĩa với việc dữ liệu phải rollback (trở lại) trạng thái ban đầu.

### 6. Abstract class, interface, namespace và trait là gì?

    - [Abstract class](https://nhaancs.wordpress.com/2016/06/09/php-oop-bai-7-class-abstract/)
    - [Namespace](https://nhaancs.wordpress.com/2016/06/09/php-oop-bai-8-interface/)
    - [Interface](https://nhaancs.wordpress.com/2016/06/09/php-oop-bai-8-interface/)
    - [Traits](https://nhaancs.wordpress.com/2016/06/09/php-oop-bai-9-traits/)

### 7. ORM, MVC là gì?

    - ORM (Object Relational Mapping) là kỹ thuật chuyển đổi dữ liệu giữa các hệ thống khác (không phải là mô hình hướng đối tượng) sang các đối tượng trong ngôn ngữ lập trình hướng đối tượng. Ví dụ: Chuyển dữ liệu từ các dòng dữ liệu trong CSDL quan hệ sang đối tượng.
    - MVC là viết tắt của Model – View – Controller. Là một kiến trúc phần mềm hay mô hình thiết kế được sử dụng trong kỹ thuật phần mềm. Nói cho dễ hiểu, nó là mô hình phân bố source code thành 3 phần, mỗi thành phần có một nhiệm vụ riêng biệt và độc lập với các thành phần khác. **Controller** giữ nhiệm vụ nhận điều hướng các yêu cầu từ người dùng và gọi đúng những phương thức xử lý chúng… Chẳng hạn thành phần này sẽ nhận request từ url và form để thao tác trực tiếp với Model. **Model** là thành phần chứa tất cả các nghiệp vụ logic, phương thức xử lý, truy xuất database, đối tượng mô tả dữ liệu như các Class, hàm xử lý… **View** Đảm nhận việc hiển thị thông tin, tương tác với người dùng, nơi chứa tất cả các đối tượng GUI như textbox, images… Hiểu một cách đơn giản, nó là tập hợp các form hoặc các file HTML.

### 8. Sau khi thực hiện đoạn mã trên kết quả hiển thị sẽ là gì?

    ```
    <?php
        $a=5;
        $b=12;
        $c=10;
        $d=7;
        $e=($a*$b)+$c*$d/$a;
        print($e); // 74
    ?>
    ```
### 9. Sau khi thực hiện đoạn mã trên kết quả hiển thị sẽ là gì?

    ```
    <?php
        $b = false;
        if($b = true)
            print("true");
        else
            print("false");
        // true
    ?>
    ```
### 10. Sau khi thực hiện đoạn mã trên kết quả hiển thị sẽ là gì?

    ```
    <?php
        for($x = 1; $x <= 2; $x++){
            for($y = 1; $y <= 3; $y++){
                if ($x == $y) continue;
                print("x = $x y = $y");
            }
        }
        // $x = 1 y = 2
        // $x = 1 y = 3
        // $x = 2 y = 1
        // $x = 2 y = 3
    ?>
    ```
### 11. Sau khi thực hiện đoạn mã trên kết quả hiển thị sẽ là gì?

    ```
    <?php
        echo (int) "1235Jason";
        // 1235
    ?>
    ```
### 12. Sau khi thực hiện đoạn mã trên kết quả hiển thị sẽ là gì?

    ```
    <?php
        $array = array("a1"=>'x',"a2"=>'e',"a3"=>'z');
        asort( $array );
        foreach ( $array as $keys => $values ){
            print "$keys = $values";
        }
        // a2 = e a1 = x a3 = z
    ?>
    ```
### 13. Sau khi thực hiện đoạn mã trên kết quả hiển thị sẽ là gì?

    ```
    <?php
        $array = array("a1"=>x,"a2"=>e,"a3"=>z);
        ksort( $array );
        foreach ( $array as $keys => $values ) {
            print "$keys = $values ";
        }
        // a1 = x a2 = e a3 = z
    ?>
    ```
### 14. Sau khi thực hiện đoạn mã trên kết quả hiển thị sẽ là gì?

    ```
    <?php
        $array1 = array("a", "b", "c", "d", "e", "f");
        $array2 = array_slice($array1, -3);
        foreach ( $array2 as $val ) {
            print "$val ";
        }
        // d e f
    ?>
    ```
### 15. Sau khi thực hiện đoạn mã trên kết quả hiển thị sẽ là gì?

    ```
    <?php
        $s = '13149';
        $s[$s[1]] = $s[1]+$s[3];
        print_r($s);
        // 13179
    ?>
    ```
### 16. Sau khi thực hiện đoạn mã trên kết quả hiển thị sẽ là gì?

    ```
    <?php
        if ( preg_match("/[^a-z589]+/", "AB
            asdfg589nmGH", $array) ) {
            print "<pre>\n";
            print_r( $array[0] );
            print "</pre>\n";
        }
        // AB
    ?>
    ```
### 16. Sau khi thực hiện đoạn mã trên kết quả hiển thị sẽ là gì?

    ```
    <?php
        $str = "It's \"good\"";
        echo strlen(addslashes($str));
        // 14
    ?>
    ```
