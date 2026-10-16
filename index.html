<?php
/**
 * ============================================================
 * File      : index.php
 * Deskripsi : Tugas-3 Algoritma & Struktur Data
 *             - Sorting  : Bubble Sort & Selection Sort
 *             - Searching: Linear Search & Binary Search
 *             - Struktur : Stack (LIFO) & Queue (FIFO)
 *             - Profiling waktu eksekusi + optimasi sederhana
 * Penulis   : Kelompok 6
 * Versi     : 1.0
 * Catatan perubahan:
 *   v1.0 (16 Okt 2026) - Versi awal
 * ============================================================
 */

session_start(); // dipakai supaya isi stack & queue tidak hilang saat halaman reload

// ===== BAGIAN 1: FUNGSI-FUNGSI ALGORITMA =====

/**
 * Mengubah teks "5, 3, 8" menjadi array angka [5, 3, 8].
 * Item yang bukan angka akan dibuang.
 */
function parseAngka(string $teks): array {
    $hasil = [];
    foreach (explode(",", $teks) as $item) {
        $item = trim($item);
        if ($item !== "" && is_numeric($item)) {
            $hasil[] = $item + 0; // +0 mengubah teks jadi angka
        }
    }
    return $hasil;
}

/**
 * Bubble Sort biasa: bandingkan 2 angka bersebelahan, tukar kalau salah urutan.
 * Return: [array terurut, jumlah perbandingan]
 */
function bubbleSort(array $data): array {
    $n = count($data);
    $banding = 0;
    for ($i = 0; $i < $n - 1; $i++) {
        for ($j = 0; $j < $n - $i - 1; $j++) {
            $banding++;
            if ($data[$j] > $data[$j + 1]) {
                $temp = $data[$j];
                $data[$j] = $data[$j + 1];
                $data[$j + 1] = $temp;
            }
        }
    }
    return [$data, $banding];
}

/**
 * Bubble Sort OPTIMASI: kalau dalam 1 putaran tidak ada tukar-menukar,
 * berarti data sudah urut, jadi berhenti lebih awal (lebih efisien).
 * Return: [array terurut, jumlah perbandingan]
 */
function bubbleSortOptimasi(array $data): array {
    $n = count($data);
    $banding = 0;
    for ($i = 0; $i < $n - 1; $i++) {
        $adaTukar = false;
        for ($j = 0; $j < $n - $i - 1; $j++) {
            $banding++;
            if ($data[$j] > $data[$j + 1]) {
                $temp = $data[$j];
                $data[$j] = $data[$j + 1];
                $data[$j + 1] = $temp;
                $adaTukar = true;
            }
        }
        if (!$adaTukar) {
            break;
        }
    }
    return [$data, $banding];
}

/**
 * Selection Sort: cari angka terkecil, taruh di posisi paling depan, ulangi.
 * Return: [array terurut, jumlah perbandingan]
 */
function selectionSort(array $data): array {
    $n = count($data);
    $banding = 0;
    for ($i = 0; $i < $n - 1; $i++) {
        $min = $i;
        for ($j = $i + 1; $j < $n; $j++) {
            $banding++;
            if ($data[$j] < $data[$min]) {
                $min = $j;
            }
        }
        if ($min !== $i) {
            $temp = $data[$i];
            $data[$i] = $data[$min];
            $data[$min] = $temp;
        }
    }
    return [$data, $banding];
}

/**
 * Linear Search: cek satu per satu dari depan sampai ketemu.
 * Return: [indeks (-1 kalau tidak ada), jumlah langkah]
 */
function linearSearch(array $data, $cari): array {
    $langkah = 0;
    foreach ($data as $i => $nilai) {
        $langkah++;
        if ($nilai == $cari) {
            return [$i, $langkah];
        }
    }
    return [-1, $langkah];
}

/**
 * Binary Search: SYARAT array sudah terurut.
 * Cek tengah, lalu buang separuh yang tidak mungkin berisi angka dicari.
 * Return: [indeks (-1 kalau tidak ada), jumlah langkah]
 */
function binarySearch(array $data, $cari): array {
    $kiri = 0;
    $kanan = count($data) - 1;
    $langkah = 0;
    while ($kiri <= $kanan) {
        $langkah++;
        $tengah = intdiv($kiri + $kanan, 2);
        if ($data[$tengah] == $cari) {
            return [$tengah, $langkah];
        } elseif ($data[$tengah] < $cari) {
            $kiri = $tengah + 1;
        } else {
            $kanan = $tengah - 1;
        }
    }
    return [-1, $langkah];
}

/**
 * Profiling: ukur waktu eksekusi sebuah fungsi sorting (dalam mikrodetik).
 * Return: [hasil, jumlah perbandingan, waktu mikrodetik]
 */
function profil(string $namaFungsi, array $data): array {
    $mulai = hrtime(true); // waktu dalam nanodetik
    [$hasil, $banding] = $namaFungsi($data);
    $selesai = hrtime(true);
    return [$hasil, $banding, ($selesai - $mulai) / 1000];
}

/** Pengaman: tampilkan teks apa adanya, bukan sebagai kode HTML. */
function h($teks): string {
    return htmlspecialchars((string)$teks);
}

// ===== BAGIAN 2: PROSES FORM =====

$_SESSION["stack"] = $_SESSION["stack"] ?? [];
$_SESSION["queue"] = $_SESSION["queue"] ?? [];

$angkaInput = "";
$cariInput = "";
$daftarSort = [];
$infoCari = null;
$pesanInput = "";

if ($_SERVER["REQUEST_METHOD"] === "POST") {
    $aksi = $_POST["aksi"] ?? "";

    if ($aksi === "proses") {
        // --- Sorting & searching (tanpa redirect, hasil langsung tampil) ---
        $angkaInput = trim($_POST["angka"] ?? "");
        $cariInput = trim($_POST["cari"] ?? "");
        $data = parseAngka($angkaInput);

        if (count($data) === 0) {
            $pesanInput = "Isi minimal 1 angka ya, pisahkan pakai koma.";
        } else {
            $daftarSort["Bubble Sort"] = profil("bubbleSort", $data);
            $daftarSort["Bubble Sort (optimasi)"] = profil("bubbleSortOptimasi", $data);
            $daftarSort["Selection Sort"] = profil("selectionSort", $data);

            if ($cariInput !== "" && is_numeric($cariInput)) {
                $target = $cariInput + 0;
                $terurut = $daftarSort["Selection Sort"][0];
                $infoCari = [
                    "target" => $target,
                    "terurut" => $terurut,
                    "linear" => linearSearch($data, $target),
                    "binary" => binarySearch($terurut, $target),
                ];
            }
        }
    } else {
        // --- Stack & Queue (pakai redirect supaya refresh tidak kirim ulang) ---
        $teks = trim($_POST["teks"] ?? "");

        if ($aksi === "push" && $teks !== "") {
            $_SESSION["stack"][] = $teks;
        } elseif ($aksi === "pop") {
            $_SESSION["pesan"] = count($_SESSION["stack"]) > 0
                ? "Pop: \"" . array_pop($_SESSION["stack"]) . "\" keluar dari stack"
                : "Stack masih kosong";
        } elseif ($aksi === "enqueue" && $teks !== "") {
            $_SESSION["queue"][] = $teks;
        } elseif ($aksi === "dequeue") {
            $_SESSION["pesan"] = count($_SESSION["queue"]) > 0
                ? "Dequeue: \"" . array_shift($_SESSION["queue"]) . "\" keluar dari queue"
                : "Queue masih kosong";
        } elseif ($aksi === "reset") {
            $_SESSION["stack"] = [];
            $_SESSION["queue"] = [];
        }

        header("Location: index.php");
        exit;
    }
}

$pesanSession = $_SESSION["pesan"] ?? "";
unset($_SESSION["pesan"]);
?>
<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Tugas-3 Algoritma</title>
  <style>
    body { font-family: sans-serif; background: #f0f2f5; display: flex; justify-content: center; padding: 16px; }
    .app { width: 100%; max-width: 600px; }
    .kartu { background: white; padding: 16px; border-radius: 12px; box-shadow: 0 2px 10px rgba(0,0,0,.1); margin-bottom: 16px; }
    h1 { text-align: center; margin-top: 0; }
    h2 { margin-top: 0; font-size: 18px; }
    input[type=text] { width: 100%; box-sizing: border-box; padding: 10px; border: 1px solid #ccc; border-radius: 8px; font-size: 16px; margin-bottom: 8px; }
    button { padding: 10px 14px; border: none; border-radius: 8px; background: #4f46e5; color: white; font-size: 15px; cursor: pointer; margin-right: 4px; margin-top: 4px; }
    button.merah { background: #ef4444; }
    table { width: 100%; border-collapse: collapse; font-size: 14px; }
    th, td { border: 1px solid #ddd; padding: 6px; text-align: left; vertical-align: top; }
    th { background: #eef; }
    .info { color: #555; font-size: 14px; }
    .pesan { background: #fef3c7; padding: 8px; border-radius: 8px; margin-bottom: 8px; }
    .kotak { display: inline-block; background: #e0e7ff; padding: 4px 10px; border-radius: 6px; margin: 2px; }
  </style>
</head>
<body>
<div class="app">
  <h1>Tugas-3 Algoritma</h1>

  <!-- ===== BAGIAN 3: SORTING + SEARCHING + PROFILING ===== -->
  <div class="kartu">
    <h2>Sorting, Searching &amp; Profiling</h2>
    <form method="post">
      <input type="hidden" name="aksi" value="proses">
      <input type="text" name="angka" value="<?= h($angkaInput) ?>" placeholder="Angka dipisah koma, contoh: 5, 3, 8, 1, 9, 2" required>
      <input type="text" name="cari" value="<?= h($cariInput) ?>" placeholder="Angka yang dicari (boleh dikosongkan)">
      <button type="submit">Proses</button>
    </form>

    <?php if ($pesanInput !== ""): ?>
      <p class="pesan"><?= h($pesanInput) ?></p>
    <?php endif; ?>

    <?php if (count($daftarSort) > 0): ?>
      <h2 style="margin-top:16px">Hasil Sorting</h2>
      <table>
        <tr><th>Algoritma</th><th>Hasil</th><th>Banding</th><th>Waktu (µs)</th></tr>
        <?php foreach ($daftarSort as $nama => $r): ?>
          <tr>
            <td><?= h($nama) ?></td>
            <td><?= h(implode(", ", $r[0])) ?></td>
            <td><?= $r[1] ?></td>
            <td><?= number_format($r[2], 2) ?></td>
          </tr>
        <?php endforeach; ?>
      </table>
      <p class="info">Banding = jumlah perbandingan. Waktu makin kecil = makin cepat. Bubble Sort optimasi berhenti lebih awal kalau data sudah urut.</p>
    <?php endif; ?>

    <?php if ($infoCari !== null): ?>
      <h2 style="margin-top:16px">Hasil Searching: <?= h($infoCari["target"]) ?></h2>
      <table>
        <tr><th>Algoritma</th><th>Data yang dicek</th><th>Posisi</th><th>Langkah</th></tr>
        <tr>
          <td>Linear Search</td>
          <td>Data asli (belum urut)</td>
          <td><?= $infoCari["linear"][0] >= 0 ? "indeks " . $infoCari["linear"][0] : "tidak ketemu" ?></td>
          <td><?= $infoCari["linear"][1] ?></td>
        </tr>
        <tr>
          <td>Binary Search</td>
          <td><?= h(implode(", ", $infoCari["terurut"])) ?> (sudah diurutkan)</td>
          <td><?= $infoCari["binary"][0] >= 0 ? "indeks " . $infoCari["binary"][0] : "tidak ketemu" ?></td>
          <td><?= $infoCari["binary"][1] ?></td>
        </tr>
      </table>
    <?php endif; ?>
  </div>

  <!-- ===== BAGIAN 4: STACK & QUEUE ===== -->
  <div class="kartu">
    <h2>Stack (LIFO) &amp; Queue (FIFO)</h2>

    <?php if ($pesanSession !== ""): ?>
      <p class="pesan"><?= h($pesanSession) ?></p>
    <?php endif; ?>

    <form method="post">
      <input type="text" name="teks" placeholder="Isi data, contoh: Tugas A">
      <button type="submit" name="aksi" value="push">Push (Stack)</button>
      <button type="submit" name="aksi" value="pop">Pop (Stack)</button>
      <button type="submit" name="aksi" value="enqueue">Enqueue (Queue)</button>
      <button type="submit" name="aksi" value="dequeue">Dequeue (Queue)</button>
      <button type="submit" name="aksi" value="reset" class="merah">Reset</button>
    </form>

    <p><b>Stack</b> (yang masuk terakhir keluar duluan):<br>
      <?php if (count($_SESSION["stack"]) === 0): ?>
        <span class="info">kosong</span>
      <?php else: ?>
        <?php foreach (array_reverse($_SESSION["stack"]) as $i => $isi): ?>
          <span class="kotak"><?= h($isi) ?><?= $i === 0 ? " ⬅ atas" : "" ?></span>
        <?php endforeach; ?>
      <?php endif; ?>
    </p>

    <p><b>Queue</b> (yang masuk pertama keluar duluan):<br>
      <?php if (count($_SESSION["queue"]) === 0): ?>
        <span class="info">kosong</span>
      <?php else: ?>
        <?php foreach ($_SESSION["queue"] as $i => $isi): ?>
          <span class="kotak"><?= h($isi) ?><?= $i === 0 ? " ⬅ depan" : "" ?></span>
        <?php endforeach; ?>
      <?php endif; ?>
    </p>
  </div>
</div>
</body>
</html>
