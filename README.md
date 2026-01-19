# 5d-mata-lantai
// Data produk generatif
const products = [
    { name: "Lantai Interior Kayu", img: "images/interior1.jpg", desc: "Sampel layar untuk visualisasi 5D." },
    { name: "Fasad Eksterior Batu", img: "images/exterior1.jpg", desc: "Optimasi desain eksterior." },
    { name: "Dinding Interior Vinyl", img: "images/interior2.jpg", desc: "Layar interaktif untuk rumah." },
    { name: "Atap Eksterior Metal", img: "images/exterior2.jpg", desc: "Simulasi cuaca tahan lama." }
];

// Generate produk grid
const productGrid = document.getElementById('productGrid');
products.forEach(product => {
    const item = document.createElement('div');
    item.className = 'product-item';
    item.innerHTML = `
        <img src="${product.img}" alt="${product.name}">
        <h3>${product.name}</h3>
        <p>${product.desc}</p>
        <button onclick="viewProduct('${product.name}')">Lihat Detail</button>
    `;
    productGrid.appendChild(item);
});

// Fungsi untuk melihat produk
function viewProduct(name) {
    alert(`Detail untuk ${name}: Fitur simulasi 5D tersedia di aplikasi penuh.`);
}

// Simulasi zoom
function toggleZoom() {
    const img = document.getElementById('simImage');
    const desc = document.getElementById('simDesc');
    if (img.style.transform === 'scale(1.5)') {
        img.style.transform = 'scale(1)';
        desc.textContent = 'Klik gambar untuk zoom dan simulasi.';
    } else {
        img.style.transform = 'scale(1.5)';
        desc.textContent = 'Simulasi 5D: Bayangkan produk ini di rumah Anda!';
    }
}

// Scroll ke section
function scrollToSection(id) {
    document.getElementById(id).scrollIntoView({ behavior: 'smooth' });
}

// Form transaksi
document.getElementById('orderForm').addEventListener('submit', function(e) {
    e.preventDefault();
    const product = document.getElementById('product').value;
    const quantity = document.getElementById('quantity').value;
    alert(`Pesanan: ${quantity} unit ${product}. Terima kasih! (Ini simulasi; integrasikan dengan backend untuk transaksi nyata.)`);
});

// Fungsi harga
function showPrices() {
    alert('Harga: Interior - Rp 500.000/m², Eksterior - Rp 750.000/m². Hubungi untuk diskon!');
}
