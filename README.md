# Zen Porto

Portofolio web developer bertema ukiran klasik yang dibangun sebagai satu halaman statis tanpa proses build.

> **Jenis proyek:** Proyek pribadi

[![Live Demo](https://img.shields.io/badge/Live%20Demo-000000?style=for-the-badge&logo=vercel)](https://porto-2027.vercel.app)

## Ringkasan

Zen Porto adalah landing page portofolio pribadi yang seluruh isinya berada di dalam satu berkas `index.html`, tanpa framework dan tanpa proses build. Halaman menyuguhkan profil ringkas, daftar keahlian, section proyek yang divisualisasikan sebagai ASCII art, tawaran jasa, manifesto, dan kontak dalam tema ukiran klasik bergaya gothic dengan palet monokrom hitam-putih. Semua animasi — parallax, reveal saat scroll, grain berbasis WebGL, dan ASCII art — dijalankan murni di sisi klien dengan JavaScript vanilla.

## Fitur

- Hero bergaya ukiran dengan efek parallax: gambar latar bergerak mengikuti posisi pointer melalui GSAP.
- Efek mesin ketik pada subjudul hero dan pesan penutup di section Kontak yang dipicu ScrollTrigger.
- Langit hero dibangkitkan secara prosedural: 120 bintang SVG dan 8 kilat acak yang dibuat oleh JavaScript.
- Grain ring berbasis WebGL dengan shader fbm yang bereaksi terhadap posisi dan keberadaan pointer di canvas.
- ASCII reveal pada canvas yang menggambar gambar sebagai karakter ASCII dan mengikuti kursor, merupakan port vanilla dari `components/originkit/ui/ascii-reveal.tsx`.
- Mode terang dan gelap dengan tombol toggle, pilihan tema disimpan di `localStorage` dengan kunci `porto-theme`, dan gambar tinta otomatis ter-invert mengikuti tema.
- Animasi scroll per section (kelas `.reveal`), progress bar tinta di tepi atas, figur bergelantungan dengan tali yang panjangnya diukur ulang mengikuti layout.
- Backsound `backsound.mp3` dengan tombol putar dan jeda, serta menu burger untuk navigasi section di layar kecil.

## Teknologi

![HTML](https://img.shields.io/badge/HTML-E34F26?style=for-the-badge&logo=html5)
![CSS](https://img.shields.io/badge/CSS-1572B6?style=for-the-badge&logo=css)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript)
![GSAP](https://img.shields.io/badge/GSAP-77E3F4?style=for-the-badge&logo=gsap)
![Font Awesome](https://img.shields.io/badge/Font%20Awesome-538DD7?style=for-the-badge&logo=fontawesome)

Tambahan: Google Fonts (Playfair Display, Montserrat, Oswald, Dancing Script) dan WebGL untuk efek grain.

## Cara Menjalankan

Repo ini statis tanpa proses build. Unduh atau clone repo ini, lalu buka `index.html` langsung di browser. Untuk publikasi, unggah isi folder ke hosting statis seperti Vercel, GitHub Pages, atau Netlify tanpa perlu konfigurasi build.

## Struktur Proyek

```
porto-2027/
├── index.html
├── components/
│   └── originkit/
│       └── ui/
│           ├── ascii-reveal.tsx
│           └── grain-ring.tsx
├── README.md
├── LICENSE
├── .gitignore
├── hero-engraving.jpg
├── cherished-eye.jpg
├── atelier-story.jpg
├── carousel-pride.png
├── ascii-source.png
├── scatter-blossom.png
├── ornament-bg.svg
├── fig-top.png
├── fig-mid.png
├── fig-bottom.png
├── frame-tl.png
├── frame-tr.png
├── frame-bl.png
├── frame-br.png
├── backsound.mp3
└── 3.jpeg
```

## Catatan

- Ukuran repo sekitar 23,6 MB, hampir seluruhnya aset media: `carousel-pride.png` (9,4 MB), `backsound.mp3` (7,2 MB), `atelier-story.jpg` (2,4 MB), dan `ornament-bg.svg` (1,6 MB). Untuk hosting yang lebih ringan, aset berukuran besar sebaiknya dikompres atau dipindahkan ke CDN.
- `ascii-source.png` dan `3.jpeg` tidak direferensikan di `index.html`; gambar sumber ASCII sudah ditanam sebagai data base64 di dalam skrip.
- `components/originkit/ui/ascii-reveal.tsx` dan `grain-ring.tsx` adalah sumber React/TSX dari komponen yang di-port ke JavaScript vanilla di dalam `index.html`. Repo tidak memiliki `package.json`, sehingga kedua berkas `.tsx` tersebut tidak dapat dibangun apa adanya.
- Entri `.gitignore` saat ini hanya mengabaikan `.originkit/`, sedangkan lokasi folder sebenarnya adalah `components/originkit/`.
- GSAP, ScrollTrigger, dan Font Awesome dimuat dari CDN, sehingga tampilan memerlukan koneksi internet.

## Lisensi

MIT License — lihat [LICENSE](LICENSE)
