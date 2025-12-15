#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <math.h>

/* ---------- Utility ---------- */
void pause() {
    printf("\nTekan Enter untuk kembali ke menu utama...");
    getchar();
    getchar();
}

/* ---------- 1. Hukum Ohm ---------- */
void hukum_ohm() {
    char pilih;
    double V, I, R;

    printf("\n--- Kalkulator Hukum Ohm ---\n");
    printf("Hitung (V/I/R): ");
    scanf(" %c", &pilih);

    if (pilih == 'V' || pilih == 'v') {
        printf("Masukkan Arus (A): ");
        scanf("%lf", &I);
        printf("Masukkan Hambatan (Ohm): ");
        scanf("%lf", &R);
        V = I * R;
        printf("Tegangan = %.2lf Volt\n", V);
    } else if (pilih == 'I' || pilih == 'i') {
        printf("Masukkan Tegangan (V): ");
        scanf("%lf", &V);
        printf("Masukkan Hambatan (Ohm): ");
        scanf("%lf", &R);
        I = V / R;
        printf("Arus = %.2lf Ampere\n", I);
    } else if (pilih == 'R' || pilih == 'r') {
        printf("Masukkan Tegangan (V): ");
        scanf("%lf", &V);
        printf("Masukkan Arus (A): ");
        scanf("%lf", &I);
        R = V / I;
        printf("Hambatan = %.2lf Ohm\n", R);
    } else {
        printf("Pilihan tidak valid!\n");
    }
}

/* ---------- 2. Daya Listrik ---------- */
void daya_listrik() {
    double V, I;
    printf("\n--- Kalkulator Daya Listrik ---\n");
    printf("Masukkan Tegangan (V): ");
    scanf("%lf", &V);
    printf("Masukkan Arus (A): ");
    scanf("%lf", &I);
    printf("Daya = %.2lf Watt\n", V * I);
}

/* ---------- 3. Resistor Seri ---------- */
void resistor_seri() {
    int n;
    double R, total = 0;

    printf("\n--- Kalkulator Resistor Seri ---\n");
    printf("Masukkan jumlah resistor: ");
    scanf("%d", &n);

    for (int i = 1; i <= n; i++) {
        printf("Masukkan nilai Resistor %d (Ohm): ", i);
        scanf("%lf", &R);
        total += R;
    }
    printf("Total Hambatan Seri = %.2lf Ohm\n", total);
}

/* ---------- 4. Resistor Paralel ---------- */
void resistor_paralel() {
    int n;
    double R, total_inv = 0;

    printf("\n--- Kalkulator Resistor Paralel ---\n");
    printf("Masukkan jumlah resistor: ");
    scanf("%d", &n);

    for (int i = 1; i <= n; i++) {
        printf("Masukkan nilai Resistor %d (Ohm): ", i);
        scanf("%lf", &R);
        total_inv += 1.0 / R;
    }
    printf("Total Hambatan Paralel = %.2lf Ohm\n", 1.0 / total_inv);
}

/* ---------- 5. Desimal ke Basis Lain ---------- */
void desimal_konversi() {
    long long n, temp;
    int rem;
    char bin[64] = "", okt[64] = "", hex[64] = "";

    printf("\n--- Konversi dari Desimal ---\n");
    printf("Masukkan bilangan desimal: ");
    scanf("%lld", &n);

    /* Biner */
    temp = n;
    while (temp > 0) {
        char c[2];
        sprintf(c, "%d", temp % 2);
        memmove(bin + 1, bin, strlen(bin) + 1);
        bin[0] = c[0];
        temp /= 2;
    }

    /* Oktal */
    temp = n;
    while (temp > 0) {
        char c[2];
        sprintf(c, "%d", temp % 8);
        memmove(okt + 1, okt, strlen(okt) + 1);
        okt[0] = c[0];
        temp /= 8;
    }

    /* Heksadesimal */
    temp = n;
    while (temp > 0) {
        rem = temp % 16;
        char c = (rem < 10) ? rem + '0' : rem - 10 + 'A';
        memmove(hex + 1, hex, strlen(hex) + 1);
        hex[0] = c;
        temp /= 16;
    }

    printf("Hasil Konversi:\n");
    printf("- Biner : %s\n", bin);
    printf("- Oktal : %s\n", okt);
    printf("- Heksadesimal : %s\n", hex);
}

/* ---------- 6–8. Basis ke Desimal ---------- */
void basis_ke_desimal(int base) {
    char input[64];
    long long result = 0;
    int len, val;

    printf("Masukkan bilangan: ");
    scanf("%s", input);

    len = strlen(input);
    for (int i = 0; i < len; i++) {
        if (input[i] >= '0' && input[i] <= '9')
            val = input[i] - '0';
        else
            val = input[i] - 'A' + 10;

        result += val * pow(base, len - i - 1);
    }

    printf("Hasil Desimal: %lld\n", result);
}

/* ---------- Main ---------- */
int main() {
    int pilihan;

    do {
        printf("\n=================================================\n");
        printf("| TOOLKIT LENGKAP ASISTEN LABORATORIUM ELEKTRO |\n");
        printf("=================================================\n");
        printf("1. Kalkulator Hukum Ohm\n");
        printf("2. Kalkulator Daya Listrik\n");
        printf("3. Kalkulator Resistor Seri\n");
        printf("4. Kalkulator Resistor Paralel\n");
        printf("5. Desimal -> Biner / Oktal / Heksadesimal\n");
        printf("6. Biner -> Desimal\n");
        printf("7. Oktal -> Desimal\n");
        printf("8. Heksadesimal -> Desimal\n");
        printf("9. Keluar\n");
        printf("Masukkan pilihan Anda (1-9): ");
        scanf("%d", &pilihan);

        switch (pilihan) {
            case 1: hukum_ohm(); pause(); break;
            case 2: daya_listrik(); pause(); break;
            case 3: resistor_seri(); pause(); break;
            case 4: resistor_paralel(); pause(); break;
            case 5: desimal_konversi(); pause(); break;
            case 6: basis_ke_desimal(2); pause(); break;
            case 7: basis_ke_desimal(8); pause(); break;
            case 8: basis_ke_desimal(16); pause(); break;
            case 9: printf("Terima kasih telah menggunakan toolkit ini!\n"); break;
            default: printf("Pilihan tidak valid!\n"); pause();
        }
    } while (pilihan != 9);

    return 0;
}
