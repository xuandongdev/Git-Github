<H1>TRƯỜNG HỢP CHỦ DỰ ÁN:</H1>

## Step1: khởi tạo dự án
I. Tạo một dự án trên Github trước.<br>
II. Tạo dự án ở máy rồi thêm remote Github.

## Step2: Checkout new branch (đứng từ nhánh chỉnh rồi checkout sang branch làm việc mới).
2.1 Dùng $git init, $git add ., $git commit -m "...", $git branch -M main, $git remote add origin ... để link đến Repo. Dùng $git branch -M master/main để chọn branch default, trường hợp quên chưa tạo master/main mà push lên branch khác: $git checkout -b master(hoặc main tùy mục đích) để tạo branch master/main sau đó vào Github để tiến hành điều chỉnh default branch trong setting.

2.2 Nhánh main/master để chứa toàn bộ dự án, không nên push code trược tiếp trên master/main mà nên dùng $git checkout -b (tên nhánh dùng để check) để tiến hành chuyển qua nhánh kiểm tra và sau khi check hoàn chỉnh thì merge với master/main.

## Step3: Change & commit code
I. Thay đổi code theo tính năng mới.<br>
II. Add tất cả code mới.<br>
III. Tạo commit code.<br>

Dùng $git status để kiểm tra trạng thái các file đã thay đổi, dùng $git add . để thêm tất cả các file thay đổi để tiến hành commit ($git commit -m "...").

## Step4: Push code lên Github
I. Đối với chủ repo: push thẳng commit vừa tạo theo remote chính lên.<br>
II. Tạo Pull request.

4.1 Sau khi commit, tiến hành push code, dùng $git remote -v để kiểm tra các remote, dùng $git push -u origin (branch-name) để push lên branch cần push.

4.2 Tạo Pull request: thường khi push lên branch mới khác với branch default thì Github sẽ hiển thị button tạo Pull request. Trường hợp không có thông báo tạo Pull request vào nav Pull request chọn new Pull request, base sẽ là nhánh chính (thường là master/main) compare là nhánh để kiểm tra sau đó chọn create Pull request. Sau khi tạo Pull request để lại discription để mô tả chức năng vừa hoàn thành cho người cùng dự án dễ theo dõi (tùy rule của team làm việc). Kiểm tra xem Pull request có bị conflict hay không, nếu không dùng merge Pull request.

THÔNG THƯỜNG 1 PULL REQUEST NÊN CHỈ CÓ 1 COMMIT ĐỂ TRÁNH BỊ NHIỄU.

4.3 Từ lần sửa code thứ 2, đẩy code lại Pull request cũ, dùng $git add ., $git commit --amend, :wq (gộp thay đổi mới ngay vào commit trước đó), $git push origin (branch-name) -f (force update lên Pull đã có lên branch-name)

## Step5: Review & Update commit
I. Trường hợp tạo Pull request mà cần sửa code tiếp:<br>
    $git commit --amend để đảm bảo giữ cho một Pull request có tối đa 1 commit duy nhất.<br>
II. Từ lần push code thứ 2 trên cùng 1 pull thì thêm thuộc tính -f vào sau lệnh push.<br>
III. Nếu Pull code về bị conflict:<br>
    i. Sửa lại code cho hết conflict - hết lỗi.<br>
    ii. $git add .<br>
    iii. $git rebase --continue.<br>
    iv. Quay lại Step3 và $git commit --amend và push code lên tiếp như bình thường.<br>
*Bonus: $git reflog --no-abbrev, cherry pick,...<br>

Review các Pull request (sau khi code nên để 1 dòng trống cuối file) sau khi review quay về conversation để merge với nhánh master/main

## Step6: Merge Pull request 
Merge Pull request vào nhánh chính.<br>
Quay về máy local checkout + pull code.<br>
Xóa branch ở Github và máy local ($git branch -D (branch-name))<br>
Quay về Step2 để tiếp tục làm tính năng mới.<br>

<H1>TRƯỜNG HỢP DỰ ÁN THUỘC VỀ CÔNG TY, TỔ CHỨC HOẶC CÁ NHÂN KHÁC:</H1>

##  STEP1: Khởi tạo dự án
I. Folk project về Github cá nhân.<br>
II. Clone project vừa folk về máy.<br>
III. Add thêm remote chính. ($git remote add (company-name) 'link-remote-repo-company').<br>

## STEP2, STEP3 tương tự bên trên

## STEP4: Push code lên Github
I. Đối với repo ngoài đã folk về Push commit lên theo remote cá nhân.<br>
II. Mở repo gốc rồi tạo pull request.<br>
III. Pull từ repo công ty về.