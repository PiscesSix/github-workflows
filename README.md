# I. Setup repo
1. Cứ tạo một empty repo trên remote
2. Clone (tạo bản sao) về ở môi trường local (thiết lập kết nối ssh để tiện hơn trong quá trình push lên).

    ```sh
    git clone [URL Repo]
    ```

# II. Workflow
1. **Lưu ý:** 
Ta sẽ không code trên nhánh main mà thay vào đó ta sẽ tách nhánh để code, mỗi nhánh nên đặt tên là feature/<name_feature> cần code (thường là phải đứng từ nhanh dev, nếu feature mới có liên quan đến feature cũ thì đứng từ nhánh feature cũ, sau đó tạo branch mới):

    ```sh
    git checkout -b <new branch>
    ```
2. Khi push code lên tạo PR (pull request) để code được review, sau đó mới merge. Câu lệnh đẩy code lên:

    ```sh
    git push -u origin <name branch>
    ```