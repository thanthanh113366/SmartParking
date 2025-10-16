# HƯỚNG DẪN CƠ BẢN SỬ DỤNG GITHUB

## 3 lệnh hay dùng nhất
Thêm tất cả file vào giỏ hàng
```bash
git add . 
```
Viết chú thích cho giỏ hàng
```bash
git commit -m "Chu_thich"
```
Đẩy giỏ hàng (chứa các file code) lên nhánh chính (main)
```bash
git push origin main
```

## 1. GitHub là gì?

GitHub là một nền tảng lưu trữ và quản lý mã nguồn trực tuyến dựa trên hệ thống kiểm soát phiên bản Git. GitHub giúp các lập trình viên:
- Lưu trữ và sao lưu mã nguồn
- Theo dõi lịch sử thay đổi
- Cộng tác làm việc nhóm
- Chia sẻ dự án với cộng đồng

## 2. Các khái niệm cơ bản

### Repository (Repo)
- Là nơi lưu trữ toàn bộ mã nguồn và lịch sử thay đổi của dự án
- Có thể là Public (công khai) hoặc Private (riêng tư)

### Branch (Nhánh)
- Là phiên bản song song của mã nguồn
- Branch chính thường là `main` hoặc `master`
- Có thể tạo branch mới để phát triển tính năng riêng biệt

### Commit
- Là một snapshot (ảnh chụp) của mã nguồn tại một thời điểm
- Mỗi commit có một message mô tả thay đổi

## 3. Cài đặt Git

### Windows:
Tải Git từ https://git-scm.com/download/win

### macOS:
```bash
brew install git
```

### Linux (Ubuntu/Debian):
```bash
sudo apt update
sudo apt install git
```

## 4. Cấu hình Git lần đầu

```bash
git config --global user.name "Tên của bạn"
git config --global user.email "email@example.com"
```

## 5. Các lệnh Git cơ bản

### Khởi tạo repository mới
```bash
git init
```

### Clone repository từ GitHub
```bash
git clone https://github.com/username/repository-name.git
```

### Kiểm tra trạng thái
```bash
git status
```

### Thêm file vào staging area
```bash
git add filename.txt          # Thêm một file cụ thể
git add .                     # Thêm tất cả file
```

### Commit thay đổi
```bash
git commit -m "Mô tả thay đổi"
```

### Xem lịch sử commit
```bash
git log
git log --oneline            # Hiển thị ngắn gọn
```

### Xem sự khác biệt
```bash
git diff                     # So sánh với lần commit cuối
git diff filename.txt        # So sánh một file cụ thể
```

## 6. Làm việc với Remote Repository

### Thêm remote repository
```bash
git remote add origin https://github.com/username/repository-name.git
```

### Xem danh sách remote
```bash
git remote -v
```

### Push code lên GitHub
```bash
git push origin main         # Push lên branch main
git push -u origin main      # Push và set upstream lần đầu
```

### Pull code từ GitHub
```bash
git pull origin main         # Pull từ branch main
```

### Fetch thông tin mới nhất
```bash
git fetch                    # Lấy thông tin mới nhưng không merge
```

## 7. Làm việc với Branch

### Tạo branch mới
```bash
git branch feature-name      # Tạo branch mới
git checkout -b feature-name # Tạo và chuyển sang branch mới
```

### Chuyển đổi branch
```bash
git checkout branch-name
git switch branch-name       # Lệnh mới hơn
```

### Xem danh sách branch
```bash
git branch                   # Branch local
git branch -r               # Branch remote
git branch -a               # Tất cả branch
```

### Merge branch
```bash
git checkout main
git merge feature-name
```

### Xóa branch
```bash
git branch -d feature-name   # Xóa branch local
git push origin --delete feature-name  # Xóa branch remote
```

## 8. Quy trình làm việc cơ bản

1. **Clone hoặc Pull code mới nhất**
   ```bash
   git clone https://github.com/username/repo.git
   # hoặc
   git pull origin main
   ```

2. **Tạo branch mới cho tính năng**
   ```bash
   git checkout -b feature/new-feature
   ```

3. **Viết code và commit**
   ```bash
   git add .
   git commit -m "Add new feature"
   ```

4. **Push branch lên GitHub**
   ```bash
   git push origin feature/new-feature
   ```

5. **Tạo Pull Request trên GitHub**
   - Vào repository trên GitHub
   - Click "New Pull Request"
   - Chọn branch nguồn và đích
   - Viết mô tả và tạo PR

6. **Review và Merge**
   - Đồng nghiệp review code
   - Merge vào branch chính
   - Xóa branch feature

## 9. Một số lệnh hữu ích khác

### Hoàn tác thay đổi
```bash
git restore filename.txt     # Hoàn tác thay đổi chưa add
git restore --staged filename.txt  # Bỏ file khỏi staging area
git reset HEAD~1            # Hoàn tác commit cuối (giữ thay đổi)
git reset --hard HEAD~1     # Hoàn tác commit cuối (xóa thay đổi)
```

### Stash (tạm cất thay đổi)
```bash
git stash                   # Cất thay đổi
git stash pop              # Lấy lại thay đổi đã cất
git stash list             # Xem danh sách stash
```

### Tag (đánh dấu phiên bản)
```bash
git tag v1.0.0             # Tạo tag
git push origin v1.0.0     # Push tag lên GitHub
```

## 10. Các file đặc biệt

### .gitignore
File này chỉ định những file/folder nào Git sẽ bỏ qua:
```
# Bỏ qua file .env
.env

# Bỏ qua thư mục node_modules
node_modules/

# Bỏ qua tất cả file .log
*.log
```

### README.md
File mô tả dự án, hướng dẫn sử dụng, cài đặt...

## 11. GitHub Features

### Issues
- Theo dõi bug, yêu cầu tính năng
- Gán người phụ trách, nhãn, milestone

### Projects
- Quản lý dự án theo phong cách Kanban
- Theo dõi tiến độ công việc

### Actions
- CI/CD tự động
- Chạy test, build, deploy tự động

### Releases
- Phát hành phiên bản chính thức
- Đính kèm file binary, changelog

## 12. Tips và Best Practices

### Commit Messages
- Viết commit message rõ ràng, ngắn gọn
- Sử dụng tiếng Anh hoặc tiếng Việt nhất quán
- Ví dụ: "Add user authentication", "Fix login bug"

### Branch Naming
- `feature/feature-name` cho tính năng mới
- `bugfix/bug-description` cho sửa bug
- `hotfix/urgent-fix` cho sửa khẩn cấp

### Quy tắc Pull Request
- Tạo PR cho mọi thay đổi quan trọng
- Viết mô tả chi tiết về thay đổi
- Yêu cầu review từ đồng nghiệp

### Security
- Không commit password, API key
- Sử dụng file .env và .gitignore
- Enable 2FA cho tài khoản GitHub

## 13. Troubleshooting

### Lỗi thường gặp

**Conflict khi merge:**
```bash
git status                  # Xem file conflict
# Sửa conflict trong editor
git add .
git commit -m "Resolve conflict"
```

**Quên add file trước commit:**
```bash
git add forgotten-file.txt
git commit --amend --no-edit
```

**Push bị rejected:**
```bash
git pull origin main        # Pull trước
git push origin main        # Rồi push lại
```

## 14. Tài liệu tham khảo

- [GitHub Docs](https://docs.github.com/)
- [Git Documentation](https://git-scm.com/doc)
- [GitHub Desktop](https://desktop.github.com/) - GUI tool
- [GitHub CLI](https://cli.github.com/) - Command line tool

---

**Lưu ý:** Đây là hướng dẫn cơ bản. Để thành thạo GitHub, bạn cần thực hành thường xuyên và tìm hiểu thêm các tính năng nâng cao.
