<!DOCTYPE html>
<html lang="vi">

<head>

<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>DUY HIEU SHOP</title>

<script src="https://cdn.tailwindcss.com"></script>

<style>

body{
    font-family: Arial, Helvetica, sans-serif;
    background: #f0fff4;
}

.hidden{
    display: none;
}

.hero{
    background-image: url('https://images.unsplash.com/photo-1445205170230-053b83016050');
    background-size: cover;
    background-position: center;
}

.product-card img{
    transition: 0.4s;
}

.product-card:hover img{
    transform: scale(1.05);
}

/* DÁN CSS SLIDER Ở ĐÂY */

.slide{
    position: absolute;
    inset: 0;
    opacity: 0;
    transition: 1s;
}

.slide.active{
    opacity: 1;
    z-index: 2;
}

.slide-image{
    width: 100%;
    height: 100%;
    object-fit: cover;
    animation: zoomEffect 8s linear infinite;
}

@keyframes zoomEffect{

    0%{
        transform: scale(1);
    }

    100%{
        transform: scale(1.1);
    }

}

.overlay{
    position: absolute;
    inset: 0;
    background: rgba(0,0,0,0.45);
}

.slide-content{
    position: absolute;
    z-index: 5;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    text-align: center;
    color: white;
}

.slide-content h1{
    font-size: 80px;
    font-weight: bold;
}

.slider-btn{
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    z-index: 10;
    width: 60px;
    height: 60px;
    font-size: 30px;
    background: rgba(255,255,255,0.3);
    color: white;
}

.left-btn{
    left: 20px;
}

.right-btn{
    right: 20px;
}

</style>

</head>

<body>

<!-- =====================================================
                        LOGIN
===================================================== -->

<section
    id="loginPage"
    class="min-h-screen flex items-center justify-center bg-green-100"
>

<div class="bg-white p-10 rounded-2xl shadow-2xl w-[420px]">

<h1 class="text-4xl font-bold text-center text-green-700 mb-8">

DUY HIEU SHOP

</h1>

<input
    type="text"
    id="username"
    placeholder="Tên đăng nhập"
    class="w-full border border-green-300 p-4 rounded-lg mb-5"
>

<input
    type="password"
    id="password"
    placeholder="Mật khẩu"
    class="w-full border border-green-300 p-4 rounded-lg mb-5"
>

<select
    id="role"
    class="w-full border border-green-300 p-4 rounded-lg mb-6"
>

<option value="Khách Hàng">

Khách Hàng

</option>

<option value="Nhân Viên">

Nhân Viên

</option>

<option value="Chủ Cửa Hàng">

Chủ Cửa Hàng

</option>

</select>

<button
    type="button"
    onclick="login()"
    class="w-full bg-green-600 hover:bg-green-700 text-white py-4 rounded-lg"
>

Đăng Nhập

</button>

<button
    type="button"
    onclick="openRegister()"
    class="w-full mt-4 bg-blue-500 hover:bg-blue-600 text-white py-4 rounded-lg"
>

Đăng Ký Tài Khoản

</button>

</div>

</section>

<!-- =====================================================
                        WEBSITE
===================================================== -->
    <div
    id="registerModal"
    class="hidden fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50"
>

<div class="bg-white p-10 rounded-2xl w-[450px]">

<h2 class="text-3xl font-bold text-green-700 mb-6">

Đăng Ký Tài Khoản

</h2>

<input
    type="text"
    id="registerUsername"
    placeholder="Tên đăng nhập"
    class="w-full border border-green-300 p-4 rounded-lg mb-5"
>

<input
    type="password"
    id="registerPassword"
    placeholder="Mật khẩu"
    class="w-full border border-green-300 p-4 rounded-lg mb-5"
>

<button
    type="button"
    onclick="registerAccount()"
    class="w-full bg-green-600 hover:bg-green-700 text-white py-4 rounded-lg mb-4"
>

Đăng Ký

</button>

<button
    type="button"
    onclick="closeRegister()"
    class="w-full bg-red-500 hover:bg-red-600 text-white py-4 rounded-lg"
>

Hủy

</button>

</div>

</div>
<div id="shopPage" style="display:none;">

<!-- =====================================================
                        HEADER
===================================================== -->

<header class="fixed top-0 left-0 w-full bg-green-100 shadow-lg z-50">

<div class="max-w-7xl mx-auto px-6 py-5 flex justify-between items-center">

<div class="flex gap-6 font-bold text-green-900">

<button onclick="showSection('homeSection')">

Trang Chủ

</button>

<button onclick="showSection('productSection')">

Sản Phẩm

</button>

<button onclick="showSection('billSection')">

Hóa Đơn

</button>

<button onclick="openKho()">

Kho

</button>

<button onclick="openOrders()">

Đơn Hàng

</button>

<button onclick="openHistory()">

Lịch Sử

</button>

</div>

<div class="flex gap-3">

<button
    onclick="shareWebsite()"
    class="bg-blue-500 hover:bg-blue-600 text-white px-5 py-3 rounded-lg"
>

Chia Sẻ

</button>

<button
    onclick="logout()"
    class="bg-red-500 hover:bg-red-600 text-white px-5 py-3 rounded-lg"
>

Đăng Xuất

</button>

</div>

</div>

</header>

<!-- =====================================================
                        HOME
===================================================== -->

<section
    id="homeSection"
    class="pt-24"
>

<!-- HERO SLIDER -->

<div class="relative w-full h-screen overflow-hidden">

    <!-- SLIDES -->

    <div id="slider">

        <!-- SLIDE 1 -->

        <div class="slide active">

            <img
                src="https://images.unsplash.com/photo-1441986300917-64674bd600d8?q=80&w=2070&auto=format&fit=crop"
                class="slide-image"
            >

            <div class="overlay"></div>

            <div class="slide-content">

                <h1>
                    DUY HIEU SHOP
                </h1>

                <p>
                    THỜI TRANG NAM & NỮ CAO CẤP
                </p>

                <button onclick="showSection('productSection')">
                    MUA NGAY
                </button>

            </div>

        </div>

        <!-- SLIDE 2 -->

        <div class="slide">

            <img
                src="https://images.unsplash.com/photo-1523381210434-271e8be1f52b?q=80&w=2070&auto=format&fit=crop"
                class="slide-image"
            >

            <div class="overlay"></div>

            <div class="slide-content">

                <h1>
                    XU HƯỚNG 2026
                </h1>

                <p>
                    PHONG CÁCH TRẺ TRUNG HIỆN ĐẠI
                </p>

                <button onclick="showSection('productSection')">
                    KHÁM PHÁ
                </button>

            </div>

        </div>

        <!-- SLIDE 3 -->

        <div class="slide">

            <img
                src="https://images.unsplash.com/photo-1496747611176-843222e1e57c?q=80&w=2070&auto=format&fit=crop"
                class="slide-image"
            >

            <div class="overlay"></div>

            <div class="slide-content">

                <h1>
                    GIẢM GIÁ SIÊU HOT
                </h1>

                <p>
                    ƯU ĐÃI ĐẾN 50%
                </p>

                <button onclick="showSection('productSection')">
                    XEM NGAY
                </button>

            </div>

        </div>

    </div>

    <!-- BUTTON -->

    <button class="slider-btn left-btn" onclick="prevSlide()">
        ❮
    </button>

    <button class="slider-btn right-btn" onclick="nextSlide()">
        ❯
    </button>

</div>

<!-- FEATURE -->

<section class="bg-white py-24">

    <div class="max-w-7xl mx-auto px-6">

        <h2 class="text-5xl font-bold text-center text-green-800 mb-16">

            SẢN PHẨM NỔI BẬT

        </h2>

        <div class="grid md:grid-cols-3 gap-10">

            <div class="bg-green-50 rounded-3xl overflow-hidden shadow-xl hover:scale-105 duration-500">

                <img
                    src="https://images.unsplash.com/photo-1483985988355-763728e1935b?q=80&w=1200&auto=format&fit=crop"
                    class="w-full h-[450px] object-cover"
                >

                <div class="p-8">

                    <h3 class="text-3xl font-bold text-green-700 mb-4">
                        Áo Thun
                    </h3>

                    <p class="text-gray-600 mb-5">
                        Thiết kế trẻ trung hiện đại
                    </p>

                    <button
                        onclick="showSection('productSection')"
                        class="bg-green-600 hover:bg-green-700 text-white px-8 py-3 rounded-xl"
                    >
                        Xem Ngay
                    </button>

                </div>

            </div>

            <div class="bg-green-50 rounded-3xl overflow-hidden shadow-xl hover:scale-105 duration-500">

                <img
                    src="https://images.unsplash.com/photo-1529139574466-a303027c1d8b?q=80&w=1200&auto=format&fit=crop"
                    class="w-full h-[450px] object-cover"
                >

                <div class="p-8">

                    <h3 class="text-3xl font-bold text-green-700 mb-4">
                        Váy Nữ
                    </h3>

                    <p class="text-gray-600 mb-5">
                        Phong cách Hàn Quốc cao cấp
                    </p>

                    <button
                        onclick="showSection('productSection')"
                        class="bg-green-600 hover:bg-green-700 text-white px-8 py-3 rounded-xl"
                    >
                        Xem Ngay
                    </button>

                </div>

            </div>

            <div class="bg-green-50 rounded-3xl overflow-hidden shadow-xl hover:scale-105 duration-500">

                <img
                    src="https://images.unsplash.com/photo-1515886657613-9f3515b0c78f?q=80&w=1200&auto=format&fit=crop"
                    class="w-full h-[450px] object-cover"
                >

                <div class="p-8">

                    <h3 class="text-3xl font-bold text-green-700 mb-4">
                        Túi Xách
                    </h3>

                    <p class="text-gray-600 mb-5">
                        Sang trọng và thời trang
                    </p>

                    <button
                        onclick="showSection('productSection')"
                        class="bg-green-600 hover:bg-green-700 text-white px-8 py-3 rounded-xl"
                    >
                        Xem Ngay
                    </button>

                </div>

            </div>

        </div>

    </div>

</section>

</section>

<!-- =====================================================
                        PRODUCTS
===================================================== -->

<section
    id="productSection"
    class="hidden pt-32 py-20 bg-green-50 min-h-screen"
>

<div class="max-w-7xl mx-auto px-6">

<button
    onclick="backHome()"
    class="mb-8 bg-gray-500 hover:bg-gray-600 text-white px-6 py-3 rounded-lg"
>

Back

</button>

<!-- GIỎ -->

<div class="bg-white p-6 rounded-2xl shadow-lg mb-10">

<div class="flex justify-between items-center">

<h3 class="text-3xl font-bold text-green-700">

Giỏ Hàng

</h3>
<div class="flex gap-4 mb-8 mt-5">
    <input type="text"
           id="searchCart"
           placeholder="Tìm kiếm sản phẩm..."
           onkeyup="searchCart()"
           class="flex-1 border border-green-300 px-5 py-4 rounded-xl outline-none">
    <button class="bg-green-600 text-white px-6 py-4 rounded-xl">
        Tìm Kiếm

    </button>
</div>
<button
    onclick="checkout()"
    class="bg-green-600 hover:bg-green-700 text-white px-8 py-3 rounded-lg"
>

Thanh Toán

</button>

</div>

<div id="cartList" class="mt-6 space-y-4">

<p class="text-gray-500">

Chưa có sản phẩm nào

</p>

</div>

</div>

<!-- SẢN PHẨM -->

<div
    id="productContainer"
    class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-8"
>

</div>

</div>

</section>

<!-- =====================================================
                        KHO
===================================================== -->

<section
    id="khoSection"
    class="hidden pt-32 py-20 bg-green-50 min-h-screen"
>

<div class="max-w-6xl mx-auto bg-white p-10 rounded-2xl shadow-xl">

<button
    onclick="backHome()"
    class="mb-8 bg-gray-500 hover:bg-gray-600 text-white px-6 py-3 rounded-lg"
>

Back

</button>

<h2 class="text-5xl font-bold text-green-800 mb-10">

Kho Sản Phẩm

</h2>

<div class="grid md:grid-cols-2 gap-6 mb-8">

<input
    type="text"
    id="newName"
    placeholder="Tên sản phẩm"
    class="border border-green-300 p-4 rounded-lg"
>

<input
    type="number"
    id="newPrice"
    placeholder="Đơn giá"
    class="border border-green-300 p-4 rounded-lg"
>

<input
    type="number"
    id="newStock"
    placeholder="Số lượng"
    class="border border-green-300 p-4 rounded-lg"
>

<input
    type="file"
    id="newImage"
    accept="image/*"
    class="border border-green-300 p-4 rounded-lg"
>

</div>

<textarea
    id="newDescription"
    rows="4"
    placeholder="Mô tả sản phẩm"
    class="w-full border border-green-300 p-4 rounded-lg"
></textarea>

<button
    onclick="addProduct()"
    class="w-full bg-green-600 hover:bg-green-700 text-white py-4 rounded-lg mt-6"
>

Thêm Sản Phẩm

</button>

<table class="w-full mt-10 border border-collapse">

<tr class="bg-green-200">

<th class="border p-4">

Tên

</th>

<th class="border p-4">

Tồn Kho

</th>

<th class="border p-4">

Quản Lý

</th>

</tr>

<tbody id="stockTable"></tbody>

</table>

</div>

</section>

<!-- =====================================================
                        ĐƠN HÀNG
===================================================== -->

<section
    id="orderSection"
    class="hidden pt-32 py-20 bg-white min-h-screen"
>

<div class="max-w-6xl mx-auto bg-green-50 p-10 rounded-2xl shadow-xl">

<button
    onclick="backHome()"
    class="mb-8 bg-gray-500 hover:bg-gray-600 text-white px-6 py-3 rounded-lg"
>

Back

</button>

<h2 class="text-5xl font-bold text-green-800 mb-10">

Đơn Hàng

</h2>

<div id="orderContent"></div>

</div>

</section>

<!-- =====================================================
                        HÓA ĐƠN
===================================================== -->

<section
    id="billSection"
    class="hidden pt-32 py-20 bg-white min-h-screen"
>

<div class="max-w-5xl mx-auto bg-green-50 p-10 rounded-2xl shadow-xl">

<button
    onclick="backHome()"
    class="mb-8 bg-gray-500 hover:bg-gray-600 text-white px-6 py-3 rounded-lg"
>

Back

</button>

<h2 class="text-5xl font-bold text-green-800 mb-10">

Hóa Đơn

</h2>

<div id="billContent"></div>

</div>

</section>

<!-- =====================================================
                        LỊCH SỬ
===================================================== -->

<section
    id="historySection"
    class="hidden pt-32 py-20 bg-white min-h-screen"
>

<div class="max-w-6xl mx-auto bg-green-50 p-10 rounded-2xl shadow-xl">

<button
    onclick="backHome()"
    class="mb-8 bg-gray-500 hover:bg-gray-600 text-white px-6 py-3 rounded-lg"
>

Back

</button>

<h2 class="text-5xl font-bold text-green-800 mb-10">

Lịch Sử

</h2>

<div id="historyContent"></div>

</div>

</section>

<!-- =====================================================
                    MODAL MUA HÀNG
===================================================== -->

<div
    id="buyModal"
    class="hidden fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50"
>

<div class="bg-white p-10 rounded-2xl w-[450px]">

<button
    onclick="closeBuyModal()"
    class="mb-5 bg-red-500 hover:bg-red-600 text-white px-5 py-2 rounded-lg"
>

Hủy

</button>

<h2 class="text-3xl font-bold text-green-700 mb-6">

Mua Sản Phẩm

</h2>

<select
    id="sizeSelect"
    class="w-full border border-green-300 p-4 rounded-lg mb-5"
>

<option>S</option>
<option>M</option>
<option>L</option>
<option>XL</option>

</select>

<input
    type="number"
    id="quantityInput"
    placeholder="Nhập số lượng"
    class="w-full border border-green-300 p-4 rounded-lg mb-5"
>

<p
    id="stockError"
    class="text-red-500 font-bold mb-5 hidden"
>

Số lượng hàng tồn kho không đủ!

</p>

<button
    onclick="addToCart()"
    class="w-full bg-green-600 hover:bg-green-700 text-white py-4 rounded-lg"
>

Thêm Vào Giỏ

</button>

</div>

</div>

<!-- =====================================================
                    THANH TOÁN
===================================================== -->

<div
    id="paymentModal"
    class="hidden fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50"
>

<div class="bg-white p-10 rounded-2xl w-[650px] max-h-[90vh] overflow-y-auto">

<button
    onclick="closePaymentModal()"
    class="mb-5 bg-red-500 hover:bg-red-600 text-white px-5 py-2 rounded-lg"
>

Hủy

</button>

<h2 class="text-4xl font-bold text-green-700 mb-8">

Thông Tin Đơn Hàng

</h2>

<div id="paymentInfo" class="mb-8"></div>

<div class="space-y-5">

<input
    type="text"
    id="customerName"
    placeholder="Tên khách hàng"
    class="w-full border border-green-300 p-4 rounded-lg"
>

<input
    type="text"
    id="phoneNumber"
    placeholder="Số điện thoại"
    class="w-full border border-green-300 p-4 rounded-lg"
>

<input
    type="text"
    id="houseNumber"
    placeholder="Số nhà"
    class="w-full border border-green-300 p-4 rounded-lg"
>

<input
    type="text"
    id="streetName"
    placeholder="Tên đường"
    class="w-full border border-green-300 p-4 rounded-lg"
>

<input
    type="text"
    id="district"
    placeholder="Quận / Huyện"
    class="w-full border border-green-300 p-4 rounded-lg"
>

<input
    type="text"
    id="city"
    placeholder="Tỉnh / Thành phố"
    class="w-full border border-green-300 p-4 rounded-lg"
>

</div>

<div class="grid grid-cols-2 gap-5 mt-8">

<button
    onclick="cashOnDelivery()"
    class="bg-green-600 hover:bg-green-700 text-white py-4 rounded-lg"
>

Thanh Toán Khi Nhận

</button>

<button
    onclick="bankPayment()"
    class="bg-blue-600 hover:bg-blue-700 text-white py-4 rounded-lg"
>

Thanh Toán Ngân Hàng

</button>

</div>

<div
    id="bankBox"
    class="hidden mt-8 bg-green-50 p-6 rounded-2xl border border-green-300"
>

<h3 class="text-2xl font-bold text-green-700 mb-5">

Thông Tin Chuyển Khoản

</h3>

<img
    src="data:image/jpeg;base64,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"
    class="w-[250px] mx-auto mb-5"
>

<p><b>Ngân hàng:</b> MB BANK</p>
<p><b>STK:</b> 2206200677777</p>
<p><b>Chủ TK:</b> TRAN DUY HIEU</p>

<button
    onclick="confirmBankPayment()"
    class="w-full mt-6 bg-blue-600 hover:bg-blue-700 text-white py-4 rounded-lg"
>

Tôi Đã Chuyển Khoản

</button>

</div>

</div>

</div>
    <!-- REGISTER MODAL -->


<script>

let currentRole = "";

let selectedProduct = null;

let cart = [];

let products =
JSON.parse(localStorage.getItem("products")) || [

{
name: "Váy Nữ Hàn Quốc",
price: 850000,
stock: 20,
description: "Váy nữ cao cấp",
image: "https://images.unsplash.com/photo-1529139574466-a303027c1d8b"
},

{
name: "Áo Thun",
price: 350000,
stock: 40,
description: "Áo thun cotton",
image: "https://images.unsplash.com/photo-1483985988355-763728e1935b"
}

];

let orders =
JSON.parse(localStorage.getItem("orders")) || [];

let historyData =
JSON.parse(localStorage.getItem("historyData")) || [];

let accounts =
JSON.parse(localStorage.getItem("accounts")) || [

{
username: "admin",
password: "999",
role: "Chủ Cửa Hàng"
},

{
username: "nhanvien",
password: "123",
role: "Nhân Viên"
}

];

function login(){

const username =
document.getElementById("username").value.trim();

const password =
document.getElementById("password").value.trim();

const role =
document.getElementById("role").value;

const user = accounts.find(account =>

account.username === username &&
account.password === password &&
account.role === role

);

if(user){

currentRole = user.role;

document
.getElementById("loginPage")
.style.display = "none";

document
.getElementById("shopPage")
.style.display = "block";

renderProducts();
renderStock();
renderOrders();
renderHistory();
updateCart();

const savedBills =
localStorage.getItem("billData");

if(savedBills){

document
.getElementById("billContent")
.innerHTML = savedBills;

}

showSection("homeSection");

alert("Đăng nhập thành công!");

}

else{

alert("Sai tài khoản hoặc mật khẩu!");

}

}

function logout(){

if(confirm("Bạn có chắc muốn đăng xuất?")){

location.reload();

}

}

function showSection(sectionId){

document
.querySelectorAll("section")
.forEach(section => {

if(section.id != "loginPage"){

section.classList.add("hidden");

}

});

document
.getElementById(sectionId)
.classList.remove("hidden");

}

function backHome(){

showSection("homeSection");

}

function shareWebsite(){

navigator.clipboard.writeText(
window.location.href
);

alert("Đã copy link website!");

}

function openKho(){

if(
currentRole == "Nhân Viên" ||
currentRole == "Chủ Cửa Hàng"
){

showSection("khoSection");

}

else{

alert("Chỉ nhân viên và chủ shop được vào!");

}

}

function openOrders(){

showSection("orderSection");

renderOrders();

}

function openHistory(){

if(
currentRole == "Nhân Viên" ||
currentRole == "Chủ Cửa Hàng"
){

showSection("historySection");

}

else{

alert("Không có quyền truy cập!");

}

}

function renderProducts(){

let html = "";

products.forEach((product, index) => {

html += `

<div class="product-card bg-white rounded-2xl overflow-hidden shadow-lg">

<img
src="${product.image}"
class="w-full h-[400px] object-cover"
>

<div class="p-5">

<h3 class="text-2xl font-bold text-green-800 mb-3">

${product.name}

</h3>

<p class="text-gray-500 mb-3">

${product.description}

</p>

<p class="text-xl font-bold text-green-700 mb-2">

${product.price.toLocaleString()}đ

</p>

<p class="text-sm text-gray-500 mb-5">

Tồn kho: ${product.stock}

</p>

<button
onclick="openBuyModal(${index})"
class="w-full bg-green-500 hover:bg-green-600 text-white py-3 rounded-lg mb-3"
>

Mua Hàng

</button>

${
currentRole == "Nhân Viên" ||
currentRole == "Chủ Cửa Hàng"

? `

<button
onclick="changeProductName(${index})"
class="w-full bg-yellow-500 hover:bg-yellow-600 text-white py-3 rounded-lg mb-3"
>

Đổi Tên

</button>

<label
class="block w-full bg-blue-500 hover:bg-blue-600 text-white text-center py-3 rounded-lg mb-3 cursor-pointer"
>

Đổi Hình

<input
type="file"
accept="image/*"
onchange="changeImage(event, ${index})"
class="hidden"
>

</label>

<button
onclick="deleteProduct(${index})"
class="w-full bg-red-500 hover:bg-red-600 text-white py-3 rounded-lg"
>

Xóa

</button>

` : ""}

</div>

</div>

`;

});

document
.getElementById("productContainer")
.innerHTML = html;

}

function renderStock(){

let html = "";

products.forEach((product, index) => {

html += `

<tr>

<td class="border p-4">

${product.name}

</td>

<td class="border p-4">

${product.stock}

</td>

<td class="border p-4">

<button
onclick="reduceStock(${index})"
class="bg-yellow-500 text-white px-4 py-2 rounded-lg mr-2"
>

-

</button>

<button
onclick="increaseStock(${index})"
class="bg-green-500 text-white px-4 py-2 rounded-lg"
>

+

</button>

</td>

</tr>

`;

});

document
.getElementById("stockTable")
.innerHTML = html;

}

function renderHistory(){

let html = "";

historyData.forEach(item => {

html += `

<div class="border-b pb-4 mb-4">

<p class="font-bold text-green-700">

${item.action}

</p>

<p>

${item.name}

</p>

</div>

`;

});

document
.getElementById("historyContent")
.innerHTML = html;

}

function renderOrders(){

let html = "";

orders.forEach((order, index) => {

html += `

<div class="bg-white p-6 rounded-2xl shadow-lg mb-8">

<h3 class="text-2xl font-bold text-green-700 mb-4">

${order.customer}

</h3>

<p><b>SĐT:</b> ${order.phone}</p>

<p><b>Địa chỉ:</b> ${order.address}</p>

<p><b>Thanh toán:</b> ${order.payment}</p>

<p><b>Trạng thái:</b> ${order.status}</p>

<div class="mt-5">

${order.items}

</div>

${
currentRole == "Nhân Viên" ||
currentRole == "Chủ Cửa Hàng"

? `

<div class="flex gap-4 mt-5">

${order.status == "Đang chờ xác nhận" ? `

<button
onclick="acceptOrder(${index})"
class="bg-green-600 text-white px-5 py-3 rounded-lg"
>

Xác Nhận

</button>

<button
onclick="rejectOrder(${index})"
class="bg-red-500 text-white px-5 py-3 rounded-lg"
>

Từ Chối

</button>

` : order.status == "Đã xác nhận đơn hàng" ? `

<div class="bg-green-100 text-green-700 px-5 py-3 rounded-lg font-bold">

✔ Đã Xác Nhận

</div>

` : `

<div class="bg-red-100 text-red-700 px-5 py-3 rounded-lg font-bold">

✖ Đã Từ Chối

</div>

`}

</div>

` : ""}

</div>

`;

});

document
.getElementById("orderContent")
.innerHTML = html;

}

function addProduct(){

const name =
document.getElementById("newName").value;

const price =
Number(document.getElementById("newPrice").value);

const stock =
Number(document.getElementById("newStock").value);

const description =
document.getElementById("newDescription").value;

const file =
document.getElementById("newImage").files[0];

if(!file){

alert("Vui lòng chọn ảnh!");

return;

}

const reader = new FileReader();

reader.onload = function(e){

products.push({

name: name,
price: price,
stock: stock,
description: description,
image: e.target.result

});

historyData.push({

action: "Đã thêm sản phẩm",
name: name

});

saveData();

renderProducts();
renderStock();
renderHistory();

};

reader.readAsDataURL(file);

}

function changeProductName(index){

const newName = prompt("Nhập tên mới:");

if(newName){

products[index].name = newName;

saveData();

renderProducts();
renderStock();

}

}

function changeImage(event, index){

const file = event.target.files[0];

const reader = new FileReader();

reader.onload = function(e){

products[index].image = e.target.result;

saveData();

renderProducts();

};

reader.readAsDataURL(file);

}

function deleteProduct(index){

if(confirm("Bạn có chắc muốn xóa?")){

products.splice(index, 1);

saveData();

renderProducts();
renderStock();

}

}

function increaseStock(index){

products[index].stock++;

saveData();

renderProducts();
renderStock();

}

function reduceStock(index){

if(products[index].stock > 0){

products[index].stock--;

saveData();

renderProducts();
renderStock();

}

}

function openBuyModal(index){

selectedProduct = products[index];

document
.getElementById("buyModal")
.classList.remove("hidden");

document
.getElementById("stockError")
.classList.add("hidden");

}

function closeBuyModal(){

document
.getElementById("buyModal")
.classList.add("hidden");

}

function addToCart(){

const size =
document.getElementById("sizeSelect").value;

const quantity =
Number(document.getElementById("quantityInput").value);

if(quantity > selectedProduct.stock){

document
.getElementById("stockError")
.classList.remove("hidden");

return;

}

selectedProduct.stock -= quantity;

cart.push({

name: selectedProduct.name,
size: size,
quantity: quantity,
total:
selectedProduct.price * quantity

});

saveData();

renderProducts();
renderStock();
updateCart();

closeBuyModal();

}
    function searchCart() {

        const keyword =
            document
                .getElementById("searchCart")
                .value
                .toLowerCase();

        let html = "";

        cart.forEach(item => {

            if (
                item.name.toLowerCase().includes(keyword)
            ) {

                html += `

<div class="cart-item bg-white p-6 rounded-2xl shadow-lg mb-6">

<div class="flex justify-between items-center">

<div>

<h3 class="text-2xl font-bold text-green-700">

${item.name}

</h3>

<p class="text-xl mt-2">

${item.price}

</p>

</div>

</div>

</div>

`;

            }

        });

        document
            .getElementById("cartList")
            .innerHTML = html;

    }
function updateCart(){

let html = "";

cart.forEach(item => {

html += `

<div class="flex justify-between border-b pb-4">

<div>

<p class="font-bold">

${item.name}

</p>

<p>

Size: ${item.size}

</p>

<p>

SL: ${item.quantity}

</p>

</div>

<p class="font-bold text-green-700">

${item.total.toLocaleString()}đ

</p>

</div>

`;

});

document
.getElementById("cartList")
.innerHTML = html;

}

function checkout(){

let total = 0;

let html = "";

cart.forEach(item => {

total += item.total;

html += `

<div class="border-b pb-3 mb-3">

<p>${item.name}</p>

<p>Size: ${item.size}</p>

<p>SL: ${item.quantity}</p>

<p>${item.total.toLocaleString()}đ</p>

</div>

`;

});

html += `

<div class="text-2xl font-bold text-green-700">

Tổng:
${total.toLocaleString()}đ

</div>

`;

document
.getElementById("paymentInfo")
.innerHTML = html;

document
.getElementById("paymentModal")
.classList.remove("hidden");

}

function closePaymentModal(){

document
.getElementById("paymentModal")
.classList.add("hidden");

}

function cashOnDelivery(){

placeOrder(
"Thanh toán khi nhận hàng"
);

}

function bankPayment(){

document
.getElementById("bankBox")
.classList.remove("hidden");

}

function confirmBankPayment(){

placeOrder(
"Đã thanh toán ngân hàng"
);

}

function placeOrder(paymentMethod){

const customer =
document.getElementById("customerName").value;

const phone =
document.getElementById("phoneNumber").value;

const house =
document.getElementById("houseNumber").value;

const street =
document.getElementById("streetName").value;

const district =
document.getElementById("district").value;

const city =
document.getElementById("city").value;

if(
customer == "" ||
phone == "" ||
house == "" ||
street == "" ||
district == "" ||
city == ""
){

alert("Vui lòng nhập đầy đủ thông tin!");

return;

}

let orderItems = "";

let total = 0;

cart.forEach(item => {

total += item.total;

orderItems += `

<div class="border-b pb-3 mb-3">

<p>${item.name}</p>

<p>Size: ${item.size}</p>

<p>SL: ${item.quantity}</p>

<p>${item.total.toLocaleString()}đ</p>

</div>

`;

});

orders.push({

customer: customer,
phone: phone,

address:
house + ", " +
street + ", " +
district + ", " +
city,

items: orderItems,

total: total,

payment: paymentMethod,

status: "Đang chờ xác nhận"

});

localStorage.setItem(
"orders",
JSON.stringify(orders)
);

cart = [];

updateCart();

closePaymentModal();

renderOrders();

alert("Đặt hàng thành công!");

}

function acceptOrder(index){

orders[index].status =
"Đã xác nhận đơn hàng";

localStorage.setItem(
"orders",
JSON.stringify(orders)
);

const order = orders[index];

document
.getElementById("billContent")
.innerHTML += `

<div class="cart-item bg-white p-8 rounded-2xl shadow-lg mb-8">

<h3 class="text-3xl font-bold text-green-700 mb-6">

Hóa Đơn Thanh Toán

</h3>

<p><b>Khách hàng:</b> ${order.customer}</p>

<p><b>SĐT:</b> ${order.phone}</p>

<p><b>Địa chỉ:</b> ${order.address}</p>

<p><b>Thanh toán:</b> ${order.payment}</p>

<p><b>Trạng thái:</b> ${order.status}</p>

<div class="mt-5">

${order.items}

</div>

<div class="text-3xl font-bold text-green-700 mt-6">

Tổng:
${order.total.toLocaleString()}đ

</div>

</div>

`;

localStorage.setItem(

"billData",

document
.getElementById("billContent")
.innerHTML

);

renderOrders();

alert("Đã xác nhận đơn hàng!");

}

function rejectOrder(index){

orders[index].status =
"Đã từ chối đơn hàng";

localStorage.setItem(
"orders",
JSON.stringify(orders)
);

renderOrders();

alert("Đã từ chối đơn hàng!");

}

    function saveData(){

localStorage.setItem(
"products",
JSON.stringify(products)
);

localStorage.setItem(
"historyData",
JSON.stringify(historyData)
);

}

/* DÁN JAVASCRIPT SLIDER Ở ĐÂY */

    window.onload = function(){

let slides =
document.querySelectorAll(".slide");

let currentSlide = 0;

function showSlide(index){

    slides.forEach(slide => {

        slide.classList.remove("active");

    });

    slides[index].classList.add("active");

}

window.nextSlide = function(){

    currentSlide++;

    if(currentSlide >= slides.length){

        currentSlide = 0;

    }

    showSlide(currentSlide);

}

window.prevSlide = function(){

    currentSlide--;

    if(currentSlide < 0){

        currentSlide = slides.length - 1;

    }

    showSlide(currentSlide);

}

setInterval(() => {

    nextSlide();

}, 5000);

}
    function openRegister(){

document
.getElementById("registerModal")
.classList.remove("hidden");

}

function closeRegister(){

document
.getElementById("registerModal")
.classList.add("hidden");

}

function registerAccount(){

const username =
document.getElementById("registerUsername").value.trim();

const password =
document.getElementById("registerPassword").value.trim();

if(username == "" || password == ""){

alert("Vui lòng nhập đầy đủ!");

return;

}

const checkUser = accounts.find(acc =>

acc.username === username

);

if(checkUser){

alert("Tài khoản đã tồn tại!");

return;

}

accounts.push({

username: username,
password: password,
role: "Khách Hàng"

});

localStorage.setItem(

"accounts",
JSON.stringify(accounts)

);

alert("Đăng ký thành công!");

closeRegister();

}
</script>

</div>

</body>

</html>
