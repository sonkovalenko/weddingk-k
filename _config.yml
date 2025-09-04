// Burger menu
const menuToggle = document.querySelector('.menu-toggle');
const menu = document.querySelector('.menu');
if (menuToggle) {
  menuToggle.addEventListener('click', () => {
    menu.classList.toggle('open');
  });
}

// Smooth scroll
document.querySelectorAll('a[href^="#"]').forEach(a => {
  a.addEventListener('click', (e) => {
    const target = document.querySelector(a.getAttribute('href'));
    if (target) {
      e.preventDefault();
      target.scrollIntoView({ behavior: 'smooth', block: 'start' });
    }
  });
});

// AJAX submit with Formspree
const form = document.getElementById('contactForm');
if (form) {
  form.addEventListener('submit', async (e) => {
    e.preventDefault();
    const status = form.querySelector('.form-status');
    status.textContent = 'Отправляем...';
    try {
      const data = new FormData(form);
      const res = await fetch(form.action, {
        method: 'POST',
        headers: { 'Accept': 'application/json' },
        body: data
      });
      if (res.ok) {
        status.textContent = 'Спасибо! Заявка отправлена.';
        form.reset();
      } else {
        const err = await res.json().catch(() => ({}));
        status.textContent = err.error || 'Ошибка отправки. Проверьте поля.';
      }
    } catch (err) {
      status.textContent = 'Сеть недоступна. Попробуйте ещё раз.';
    }
  });
}
