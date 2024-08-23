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
2. Khi push code lên tạo PR (pull request) để code được review, sau đó mới merge.

    ```sh
    git push -u origin <name branch>
    `
# III. Stash git
Mình dùng stash git khi nào?

Giả sử, nếu ta đang code một feature_2 từ nhánh feature_1, mà ta muốn checkout lại nhánh feature_1 để sửa code và commit lên lại. Nhưng khi đó, checkout qua thì những dòng code ta mới viết ở feature_2 vẫn còn, vậy có cách nào không?

- Cách 1: Người ta sẽ dùng commit (snapshot) cho code mới, sau đó checkout lại feature_1, code như thường (_Nhứng cách này mệt ở chỗ lại phải squash những commit vô nghĩa đó_).
- Cách 2: Git Stash, cái này thú vị hơn, sẽ là nơi lưu trữ code tạm thời.

Cách sử dụng:
    
1. Add code mới vào stage.

    ```sh
    git add .
    ```

2. Sau dùng lệnh stash:
    ```sh
    git stash
    ```

3. Chuyển sang nhánh feature_1 rồi code, code xong commit lại.

4. Chuyển lại nhánh feature_2, dùng lệnh pop để lấy lại lưu trữ tạm thời.
    ```sh
    git stash pop
    ```

5. Cách để check trong stash có những stash nào:
    ```sh
    git stash list
    ```
