import java.util.ArrayList;
import java.util.Scanner;
public class Main {
    public static void main(String[] args) {
        ArrayList<String> daftarMahasiswa = new ArrayList<>();
        Scanner input = new Scanner(System.in);
        while (true) {
            System.out.print("Masukkan nama mahasiswa (ketik 'selesai' untuk berhenti): ");
            String nama = input.nextLine();

            if (nama.isEmpty()) {
                try {
                    throw new IllegalArgumentException("Nama tidak boleh kosong");
                } catch (IllegalArgumentException e) {
                    System.err.println("Error: " + e.getMessage());
                }
            } else if (nama.equalsIgnoreCase("selesai")) {
                break;
            } else {
                daftarMahasiswa.add(nama);
            }
        }

        System.out.println("\nData mahasiswa yang sudah diinput:");
        for (int i = 0; i < daftarMahasiswa.size(); i++) {
            System.out.println("Mahasiswa ke-" + (i + 1) + ": " + daftarMahasiswa.get(i));
        }
    }
}
