#include <stdio.h>
#include <stdlib.h>
#include <stdbool.h>
#include <unistd.h>

#ifdef _WIN32
#include <windows.h>
#endif

void clear_screen() {
    #ifdef _WIN32
        system("cls");
    #else
        system("clear");
    #endif
}

bool validate_dimensions(int width, int height) {
    return (width >= 10 && width <= 100 && height >= 5 && height <= 75);
}

void draw_rectangle(int width, int height) {
    for (int i = 0; i < height; i++) {
        for (int j = 0; j < width; j++) {
            if (i == 0 || i == height - 1 || j == 0 || j == width - 1) {
                printf("*");
            } else {
                printf(" ");
            }
        }
        printf("\n");
    }
}

void draw_triangle(int base) {
    for (int i = 0; i < base; i++) {
        for (int j = 0; j < base - i - 1; j++) {
            printf(" ");
        }
        for (int j = 0; j < 2 * i + 1; j++) {
            printf("*");
        }
        printf("\n");
    }
}

void draw_diamond(int width) {
    int height = width / 2;
    for (int i = 0; i < height; i++) {
        for (int j = 0; j < height - i - 1; j++) {
            printf(" ");
        }
        for (int j = 0; j < 2 * i + 1; j++) {
            printf("*");
        }
        printf("\n");
    }
    for (int i = height - 2; i >= 0; i--) {
        for (int j = 0; j < height - i - 1; j++) {
            printf(" ");
        }
        for (int j = 0; j < 2 * i + 1; j++) {
            printf("*");
        }
        printf("\n");
    }
}

void animate_rectangle(int width, int height, int frames) {
    for (int f = 0; f < frames; f++) {
        clear_screen();
        for (int i = 0; i < height; i++) {
            for (int j = 0; j < width; j++) {
                if (i == 0 || i == height - 1 || j == 0 || j == width - 1) {
                    printf(f % 2 == 0 ? "*" : "-");
                } else {
                    printf(" ");
                }
            }
            printf("\n");
        }
        usleep(500000);  // 0.5 second delay
    }
}

int main() {
    int choice, width, height;

    while (1) {
        printf("\nPilih jenis gambar:\n");
        printf("1. Persegi Panjang\n");
        printf("2. Segitiga\n");
        printf("3. Diamond\n");
        printf("4. Persegi Panjang Bergerak\n");
        printf("5. Keluar\n");
        printf("Masukkan pilihan (1-5): ");
        scanf("%d", &choice);

        if (choice == 5) {
            printf("Terima kasih telah menggunakan program ini!\n");
            break;
        }

        printf("Masukkan lebar: ");
        scanf("%d", &width);
        printf("Masukkan tinggi: ");
        scanf("%d", &height);

        if (!validate_dimensions(width, height)) {
            printf("Ukuran tidak valid. Lebar harus antara 10-100 dan tinggi antara 5-75.\n");
            continue;
        }

        switch (choice) {
            case 1:
                draw_rectangle(width, height);
                break;
            case 2:
                draw_triangle(height);
                break;
            case 3:
                draw_diamond(width);
                break;
            case 4:
                animate_rectangle(width, height, 10);
                break;
            default:
                printf("Pilihan tidak valid.\n");
        }
    }

    return 0;
}
