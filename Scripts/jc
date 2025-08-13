// Chuyển đổi giữa các phần nội dung chính
const navLinks = document.querySelectorAll('.nav-link');
const mainSections = document.querySelectorAll('.main-section');

navLinks.forEach(link => {
  link.addEventListener('click', (e) => {
    e.preventDefault();
    const sectionId = link.dataset.section;

    mainSections.forEach(section => {
      section.classList.remove('active');
    });

    const targetSection = document.getElementById(sectionId);
    if (targetSection) {
      targetSection.classList.add('active');
    }
  });
});

// --- JavaScript cho Popup Form ---
const loginBtn = document.getElementById('login-btn');
const registerBtn = document.getElementById('register-btn');
const popupOverlay = document.getElementById('popupOverlay');
const registerToggleBtn = document.getElementById('register-toggle');
const loginToggleBtn = document.getElementById('login-toggle');
const formTitle = document.getElementById('form-title');
const authForm = document.getElementById('auth-form');
const submitBtn = document.getElementById('submit-btn');

const userRoleSelect = document.getElementById('user-role-select');
const fullNameField = document.getElementById('full-name-field');
const confirmPasswordField = document.getElementById('confirm-password-field');

const fullNameInput = document.getElementById('full-name');
const usernameInput = document.getElementById('username');
const passwordInput = document.getElementById('password');
const confirmPasswordInput = document.getElementById('confirm-password');

const errorMsg = document.getElementById('error-msg');
    
let isRegisterMode = true;

// Mở popup và chuyển sang chế độ tương ứng
loginBtn.addEventListener('click', () => {
  openPopupWithMode('login');
});
registerBtn.addEventListener('click', () => {
  openPopupWithMode('register');
});

function openPopupWithMode(mode) {
  popupOverlay.style.display = 'flex';
  if (mode === 'login') {
    loginToggleBtn.click();
  } else {
    registerToggleBtn.click();
  }
}

function closePopup() {
  popupOverlay.style.display = 'none';
}

// Gắn sự kiện cho các nút trong form
document.getElementById('close-popup-btn').addEventListener('click', closePopup);
document.getElementById('cancel-popup-btn').addEventListener('click', closePopup);

registerToggleBtn.addEventListener('click', () => {
  isRegisterMode = true;
  registerToggleBtn.classList.add('active');
  loginToggleBtn.classList.remove('active');
  formTitle.textContent = 'Đăng ký';
  submitBtn.textContent = 'Đăng ký';
  
  userRoleSelect.style.display = 'block';
  fullNameField.style.display = 'block';
  confirmPasswordField.style.display = 'block';
  
  errorMsg.style.display = 'none';
});

loginToggleBtn.addEventListener('click', () => {
  isRegisterMode = false;
  loginToggleBtn.classList.add('active');
  registerToggleBtn.classList.remove('active');
  formTitle.textContent = 'Đăng nhập';
  submitBtn.textContent = 'Đăng nhập';
  
  userRoleSelect.style.display = 'none';
  fullNameField.style.display = 'none';
  confirmPasswordField.style.display = 'none';
  
  errorMsg.style.display = 'none';
});

authForm.addEventListener('submit', (e) => {
  e.preventDefault();

  errorMsg.textContent = '';
  errorMsg.style.display = 'none';
  
  let errorFound = false;

  if (usernameInput.value.trim() === '' || passwordInput.value.trim() === '') {
    errorMsg.textContent = 'Vui lòng điền đầy đủ Tên đăng nhập và Mật khẩu.';
    errorFound = true;
  }

  if (isRegisterMode) {
    if (fullNameInput.value.trim() === '' || confirmPasswordInput.value.trim() === '') {
      errorMsg.textContent = 'Vui lòng điền đầy đủ thông tin Đăng ký.';
      errorFound = true;
    } else if (passwordInput.value !== confirmPasswordInput.value) {
      errorMsg.textContent = 'Mật khẩu nhập lại không khớp.';
      errorFound = true;
    }
  }

  if (errorFound) {
    errorMsg.style.display = 'block';
  } else {
    alert(`Đã gửi form ${isRegisterMode ? 'Đăng ký' : 'Đăng nhập'} thành công!`);
    closePopup();
  }
});

// Hiển thị phần "Trang chủ" khi tải trang
const homeSection = document.getElementById('home');
if (homeSection) {
  homeSection.classList.add('active');
}
