# Pengolahan citra tugas pertemuan 2

# Link Youtube :

https://youtu.be/e4dkqL-4_6Y

# tugas

- impor pustaka berikut
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

- Baca gambar masukan menggunakan OpenCV:

```
img_path = ("anatomi.jpg")
img = cv2.imread("anatomi.jpg")
```

- [:,:,::-1] digunakan untuk mengonversi format BGR (digunakan oleh OpenCV) menjadi format RGB (digunakan oleh Matplotlib).

```
plt.imshow(img[:,:,::-1])
```

- Tampilkan gambar asli menggunakan Matplotlib:

```
plt.show()
```

- Tentukan empat titik masukan (inputPts) dan titik destinasi yang sesuai (outputPts) untuk transformasi perspektif:

```
inputPts = np.float32([[4,381],
                      [266,429],
                      [329,68],
                      [68,20]])

outputPts = np.float32([[0,300],
                       [300,300],
                       [300,0],
                       [0,0]])
```

- Hitung matriks transformasi perspektif (M) menggunakan cv2.getPerspectiveTransform():

```
M = cv2.getPerspectiveTransform(inputPts, outputPts)
```

- Terapkan transformasi perspektif pada gambar masukan menggunakan cv2.warpPerspective():

```
dst = cv2.warpPerspective(img, M, (300,300))
```

- Kembali, [:,:,::-1] digunakan untuk mengonversi format BGR menjadi RGB sebelum menyimpan gambar.

```
plt.imshow(dst[:,:,::-1])
```

- Simpan gambar yang telah diubah menggunakan plt.savefig() milik Matplotlib:

```
plt.savefig("output_image.png")
```

- Gambar hasil (dst) akan menjadi versi gambar yang telah mengalami transformasi perspektif.

```
plt.show()
```

# hasil nya:

![Screenshot (16)](https://github.com/Mverdy22A2/Pengolahan-citra-/assets/115523263/bb68cb38-e09b-4a1e-aa97-e6268b9bfd38)

![Screenshot (17)](https://github.com/Mverdy22A2/Pengolahan-citra-/assets/115523263/39633588-0cfc-4485-b00e-abb155c9d5c3)

![Screenshot (18)](https://github.com/Mverdy22A2/Pengolahan-citra-/assets/115523263/239c34d3-b6fc-4fe7-b4ad-97a2896faf5a)
