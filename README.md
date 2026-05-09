<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8">
  <title>ELARA Fashion</title>

  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <!-- Tailwind CSS -->
  <script src="https://cdn.tailwindcss.com"></script>

  <style>
    body{
      background:#f5f5f5;
      font-family:Arial, Helvetica, sans-serif;
    }

    .hero-bg{
      background-image:url('https://images.unsplash.com/photo-1496747611176-843222e1e57c');
      background-size:cover;
      background-position:center;
    }

    .product-card img{
      transition:0.4s;
    }

    .product-card:hover img{
      transform:scale(1.05);
    }
  </style>

</head>

<body>

<!-- =========================
     HEADER
========================= -->
<header class="fixed top-0 left-0 w-full bg-white shadow-sm z-50">

  <div class="max-w-7xl mx-auto px-6 py-4 flex justify-between items-center">

    <h1 class="text-2xl font-bold tracking-[5px] text-gray-800">
      ELARA
    </h1>

    <nav class="hidden md:flex gap-8 text-sm uppercase tracking-widest text-gray-600">
      <a href="#">Trang Chủ</a>
      <a href="#">Sản Phẩm</a>
      <a href="#">Bộ Sưu Tập</a>
      <a href="#">Liên Hệ</a>
    </nav>

  </div>

</header>

<!-- =========================
     HERO SECTION
========================= -->
<section class="hero-bg h-screen flex items-center justify-center text-white relative">

  <div class="absolute inset-0 bg-black bg-opacity-40"></div>

  <div class="relative text-center z-10 px-6">

    <h2 class="text-5xl md:text-7xl font-light mb-6">
      Summer Collection
    </h2>

    <p class="text-lg tracking-widest uppercase mb-8">
      Thời Trang Thanh Lịch 2026
    </p>

    <button class="px-10 py-4 bg-white text-black uppercase tracking-widest hover:bg-gray-200 transition">
      Khám Phá
    </button>

  </div>

</section>

<!-- =========================
     SẢN PHẨM
========================= -->
<section class="py-24 bg-white">

  <div class="max-w-7xl mx-auto px-6">

    <div class="text-center mb-16">

      <h2 class="text-4xl font-light text-gray-800 mb-4">
        Sản Phẩm Nổi Bật
      </h2>

      <p class="text-gray-500">
        Thiết kế tối giản và hiện đại
      </p>

    </div>

    <!-- GRID -->
    <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-8">

      <!-- CARD -->
      <div class="product-card bg-white shadow-sm overflow-hidden">

        <div class="overflow-hidden">

          <img
            src="https://images.unsplash.com/photo-1529139574466-a303027c1d8b"
            class="w-full h-[420px] object-cover"
          >

        </div>

        <div class="p-5">

          <h3 class="text-lg text-gray-800 mb-2">
            Váy Linen Minimalist
          </h3>

          <p class="text-sm text-gray-500 mb-4">
            Thiết kế sang trọng tối giản
          </p>

          <div class="flex justify-between items-center">

            <span class="font-semibold text-gray-800">
              1.200.000đ
            </span>

            <button class="px-4 py-2 border border-black text-xs uppercase hover:bg-black hover:text-white transition">
              Mua
            </button>

          </div>

        </div>

      </div>

      <!-- CARD -->
      <div class="product-card bg-white shadow-sm overflow-hidden">

        <div class="overflow-hidden">

          <img
            src="https://images.unsplash.com/photo-1496747611176-843222e1e57c"
            class="w-full h-[420px] object-cover"
          >

        </div>

        <div class="p-5">

          <h3 class="text-lg text-gray-800 mb-2">
            Đầm Dạ Hội ELARA
          </h3>

          <p class="text-sm text-gray-500 mb-4">
            Phong cách thời trang hiện đại
          </p>

          <div class="flex justify-between items-center">

            <span class="font-semibold text-gray-800">
              1.850.000đ
            </span>

            <button class="px-4 py-2 border border-black text-xs uppercase hover:bg-black hover:text-white transition">
              Mua
            </button>

          </div>

        </div>

      </div>

      <!-- CARD -->
      <div class="product-card bg-white shadow-sm overflow-hidden">

        <div class="overflow-hidden">

          <img
            src="https://images.unsplash.com/photo-1515886657613-9f3515b0c78f"
            class="w-full h-[420px] object-cover"
          >

        </div>

        <div class="p-5">

          <h3 class="text-lg text-gray-800 mb-2">
            Váy Satin Đen
          </h3>

          <p class="text-sm text-gray-500 mb-4">
            Tối giản và thanh lịch
          </p>

          <div class="flex justify-between items-center">

            <span class="font-semibold text-gray-800">
              990.000đ
            </span>

            <button class="px-4 py-2 border border-black text-xs uppercase hover:bg-black hover:text-white transition">
              Mua
            </button>

          </div>

        </div>

      </div>

      <!-- CARD -->
      <div class="product-card bg-white shadow-sm overflow-hidden">

        <div class="overflow-hidden">

          <img
            src="https://images.unsplash.com/photo-1483985988355-763728e1935b"
            class="w-full h-[420px] object-cover"
          >

        </div>

        <div class="p-5">

          <h3 class="text-lg text-gray-800 mb-2">
            Áo Khoác ELARA
          </h3>

          <p class="text-sm text-gray-500 mb-4">
            Phong cách Hàn Quốc
          </p>

          <div class="flex justify-between items-center">

            <span class="font-semibold text-gray-800">
              1.490.000đ
            </span>

            <button class="px-4 py-2 border border-black text-xs uppercase hover:bg-black hover:text-white transition">
              Mua
            </button>

          </div>

        </div>

      </div>

    </div>

  </div>

</section>

<!-- =========================
     FORM THÊM SẢN PHẨM
========================= -->
<section class="py-24 bg-gray-100 border-t border-gray-200">

  <div class="max-w-4xl mx-auto px-6">

    <div class="text-center mb-16">

      <p class="uppercase tracking-[5px] text-gray-400 mb-4">
        Quản Trị
      </p>

      <h2 class="text-4xl font-light text-gray-800 mb-4">
        Thêm Sản Phẩm Mới
      </h2>

      <p class="text-gray-500">
        Quản lý sản phẩm cho cửa hàng ELARA
      </p>

    </div>

    <!-- FORM -->
    <div class="bg-white p-8 md:p-12 shadow-sm">

      <!-- IMAGE -->
      <div class="mb-10">

        <h3 class="text-sm uppercase tracking-widest text-gray-700 mb-5">
          Hình Ảnh Sản Phẩm
        </h3>

        <div class="flex gap-5 overflow-x-auto">

          <!-- Upload -->
          <div class="w-40 h-52 border-2 border-dashed border-gray-300 bg-gray-50 flex flex-col justify-center items-center cursor-pointer hover:bg-gray-100 transition">

            <div class="text-5xl text-gray-400 mb-3">
              +
            </div>

            <span class="text-xs uppercase tracking-widest text-gray-500">
              Tải Ảnh
            </span>

          </div>

          <!-- Preview -->
          <div class="relative w-40 h-52 overflow-hidden bg-white shadow-sm">

            <img
              src="https://images.unsplash.com/photo-1529139574466-a303027c1d8b"
              class="w-full h-full object-cover"
            >

            <button class="absolute top-2 right-2 w-8 h-8 bg-black bg-opacity-50 text-white rounded-full">
              X
            </button>

          </div>

        </div>

      </div>

      <!-- INPUT -->
      <div class="grid md:grid-cols-2 gap-8 mb-8">

        <div>

          <label class="block text-xs uppercase tracking-widest text-gray-500 mb-3">
            Tên Sản Phẩm
          </label>

          <input
            type="text"
            placeholder="Ví dụ: Váy Linen Minimalist"
            class="w-full border border-gray-300 px-5 py-4 bg-white focus:outline-none focus:border-black"
          >

        </div>

        <div>

          <label class="block text-xs uppercase tracking-widest text-gray-500 mb-3">
            Giá
          </label>

          <input
            type="text"
            placeholder="1.200.000đ"
            class="w-full border border-gray-300 px-5 py-4 bg-white focus:outline-none focus:border-black"
          >

        </div>

      </div>

      <!-- CATEGORY -->
      <div class="mb-8">

        <label class="block text-xs uppercase tracking-widest text-gray-500 mb-3">
          Danh Mục
        </label>

        <select class="w-full border border-gray-300 px-5 py-4 bg-white focus:outline-none focus:border-black">

          <option>Váy</option>
          <option>Áo</option>
          <option>Quần</option>
          <option>Phụ Kiện</option>

        </select>

      </div>

      <!-- DESCRIPTION -->
      <div class="mb-10">

        <label class="block text-xs uppercase tracking-widest text-gray-500 mb-3">
          Mô Tả
        </label>

        <textarea
          rows="5"
          placeholder="Nhập mô tả sản phẩm..."
          class="w-full border border-gray-300 px-5 py-4 bg-white resize-none focus:outline-none focus:border-black"
        ></textarea>

      </div>

      <!-- BUTTON -->
      <div class="flex flex-col md:flex-row gap-5">

        <button class="flex-1 border border-black py-5 uppercase tracking-widest hover:bg-gray-100 transition">
          Hủy
        </button>

        <button class="flex-1 bg-black text-white py-5 uppercase tracking-widest hover:bg-gray-800 transition">
          Lưu Sản Phẩm
        </button>

      </div>

    </div>

  </div>

</section>

<!-- =========================
     FOOTER
========================= -->
<footer class="bg-black text-white py-20">

  <div class="max-w-7xl mx-auto px-6 grid md:grid-cols-4 gap-10">

    <div>

      <h2 class="text-3xl tracking-[5px] mb-6">
        ELARA
      </h2>

      <p class="text-gray-400 leading-7">
        Fashion thương hiệu hiện đại và tối giản.
      </p>

    </div>

    <div>

      <h3 class="uppercase tracking-widest mb-6">
        Menu
      </h3>

      <ul class="space-y-3 text-gray-400">
        <li>Trang Chủ</li>
        <li>Sản Phẩm</li>
        <li>Bộ Sưu Tập</li>
      </ul>

    </div>

    <div>

      <h3 class="uppercase tracking-widest mb-6">
        Liên Hệ
      </h3>

      <ul class="space-y-3 text-gray-400">
        <li>Đà Nẵng, Việt Nam</li>
        <li>0123 456 789</li>
        <li>elara@fashion.vn</li>
      </ul>

    </div>

    <div>

      <h3 class="uppercase tracking-widest mb-6">
        Theo Dõi
      </h3>

      <ul class="space-y-3 text-gray-400">
        <li>Facebook</li>
        <li>Instagram</li>
        <li>TikTok</li>
      </ul>

    </div>

  </div>

</footer>

</body>
</html>
