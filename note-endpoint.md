# Tóm tắt các endpoint của API:

* '/auth': Các chức năng liên quan đến việc xác thực người dùng
    - GET '/': Kiểm tra token để xác thực người dùng
        + 200: { message: 'Xác thực thành công' }
        + 401: { message: 'Token chưa có: Người dùng chưa đăng nhập!' }
        + 401: { message: 'Token không hợp lệ: Không thấy người dùng!' }
        + 403: { message: 'Token đã hết hạn. Hãy đăng nhập lại!' }

    - POST ‘/login’: Kiểm tra và lưu thông tin đăng nhập
        + 200: { message: 'Đăng nhập thành công', userData: { userId: user._id, fullName: user.fullName } }
        + 401: { message: 'Tên đăng nhập hoặc mật khẩu không đúng!' }
        + 500: { message: 'Lỗi hệ thống máy chủ.' }

    - POST ‘/register’: Kiểm tra và lưu thông tin đăng ký
        + 201: { message: 'Đăng ký thành công' }
        + 400: { message: 'Tên đăng nhập đã tồn tại. Hãy dùng tên khác!' }
        + 500: { message: 'Lỗi hệ thống máy chủ.' }

    - GET ‘/logout’: Đăng xuất tài khoản
        + 200: { message: 'Đăng xuất thành công' }

/----------------------------------------------------/

* '/profile': Các chức năng liên quan đến quản lý thông tin cá nhân
    - GET '/getProfile': Lấy thông tin cá nhân của người dùng
        + 200: { message: 'Lấy thông tin người dùng thành công!', user: user }
        + 404: { message: 'Không tìm thấy người dùng!' }
        + 500: { message: 'Lỗi hệ thống máy chủ.' }
    
    - PUT '/changePassword': Cập nhật mật khẩu người dùng
        + 200: { message: 'Cập nhật mật khẩu thành công!', user: updatedUser }
        + 400: { message: 'Mật khẩu cũ bị sai, hãy nhập lại!' }
        + 404: { message: 'Không tìm thấy người dùng!' }
        + 500: { message: 'Lỗi hệ thống máy chủ.' }

/----------------------------------------------------/

* '/books': Các chức năng liên quan đến việc lấy sách
    - GET '/getBooks': Lấy danh sách các sách
        + 200: { message: 'Lấy danh sách các sách thành công!', listBooks }
        + 500: { message: 'Lỗi hệ thống máy chủ!' }
    - POST '/getFilteredBooks': Lấy danh sách các sách theo tiêu chí lọc và sắp xếp
        + 200: { message: 'Lấy danh sách các sách thành công!', listBooks }
        + 500: { message: 'Lỗi hệ thống máy chủ!' }
    - POST '/getBooksByName': Lấy danh sách các sách theo tên tìm kiếm
        + 200: { message: 'Lấy danh sách các sách thành công!', listBooks }
        + 500: { message: 'Lỗi hệ thống máy chủ!' }
    - GET '/getCategories': Lấy danh sách các thể loại
        + 200: { message: 'Lấy danh sách các thể loại thành công!', categories}
        + 500: { message: 'Lỗi hệ thống máy chủ!' }
    - GET '/getAuthors': Lấy danh sách các tác giả
        + 200: { message: 'Lấy danh sách các tác giả thành công!', authors}
        + 500: { message: 'Lỗi hệ thống máy chủ!' }
    - GET '/getPublishers': Lấy danh sách các nhà xuất bản
        + 200: { message: 'Lấy danh sách các nhà xuất bản thành công!', publishers}
        + 500: { message: 'Lỗi hệ thống máy chủ!' }
