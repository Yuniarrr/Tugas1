Penggunaan OOP
A. OOP
	pembuatan program dengan menggunakan konsep objek

B. Class & Objek
	Class: kerangka dasar. Object: hasil dari Class
	COntoh: Class Hp; Object dapat berupa Samsung, Apple, dan Advan
	
	class Hp{
		// isi dr class Hp
		// isi dr class Hp
	};
	
	int main(){
		Hp samsung; // ini object
		// kode program
		return 0;
	}

C. Method
	method: perintah yang dilakukan dalam class
	contoh: menghidupkan hp, menjalankan hp
	
	class Hp{
		// isi dr class Hp
		// isi dr class Hp

		// method
		void perintah(){
			// isi dr method perintah
		}

		string perintah2(){
			// isi dr method perintah2
		}
	};
	
	int main(){
		// kode program
		// kode program
		return 0;
	}

	PARAMETERS: dalam method terdapat parameter

	class Hp{
		public:
			int parameter;
			// isi dr class Hp
			// isi dr class Hp
		
			// method
			int perintah(int _parameter){ // diletakkan dalam ()
				// isi dr method perintah
			}
		};
	
	int main(){
		// kode program
		// kode program
		return 0;
	}

D. CONSTRUCTORS
	constructors: dijalankan secara otomatis saat object dibuat

	class Hp{
		public:
			string merk;
			int nomer;
		
			// constrctors
			int Data(string _merk, int _nomer){ 
				merk = _merk;
				nomer = _nomer;
			}
		};
	
	int main(){
		Hp data1("Samsung", 19);
		cout << data1.merk << " " << data1.nomer << endl;

		return 0;
	}

E. ACCESS SPECIFIERS
	menentukan hak ases
	1. public: dapat diakses diluar kelas
	2. private: hanya dapat diakses didalam kelas
	3. protected: tidak bisa diakses diluar kelas,
		      namun dapat diakses oleh kelas dan turunan kelas

	class Hp{
		public:
			string merk;
		
			// constrctors
			int Data(string _merk){ 
				merk = _merk;
			}
	
		private:
			string nama;
			
			string hidupkanHp(){
				return "Hidupkan Hp";
			}
		
		protected:
			int kode;
		
			string matikanHp{
				return "Matikan Hp";
			}		
		};

	int main(){
		// data public
		Hp data1("Samsung", 19);
		cout << data1.merk << " " << data1.nomer << endl;
		
		// data private
		Hp data2;
		data2.nama = "Advan";
		cout << data2.nama << endl; // error
		cout << data2.hidupkanHp() << endl; error

		// data protected
		Hp data3;
		data3.kode = 1234;
		cout << data3.kode << endl; // error
		cout << data3.matikanHp << endl; // error		

		return 0;
	}
	
F. ENCAPSULATION
	encapsulation: membuat pembatasan hak akses pada data member dan member function

	class Hp{
		private:
			int kode;
		
		public:
			// setter
			void setKode(int k){
				kode = k;
			}
			
			// getter
			int getKode(){
				return kode;
			} 
	};

	int main(){
		Hp benda1;
		benda1.setKode(34567);
		cout << benda1.setKode() << endl;

		return 0;
	}

G. INHERITANCE
	inheritance: menunrunkan data member dan member function kepada kelas turunannya
	
	class Hewan{
		public:
			string nama = "Orangtua";
			string kelasPertama(){
				return "Ini dari kelas pertama";
			}
	};
	
	class Monyet: public Hewan{
		public:
			string nama2 = "Anak";
			string kelasKedua(){
				return "Ini dari kelas kedua";
			}
	};

	int main(){
		Hewan ikan;
	
		cout << ikan.nama << endl;
		cout << ikan.kelasPertama() << endl;
		cout << ikan.nama2 << endl;
		cout << ikan.kelasKedua() << endl;
	
		return 0;
	}

H. POLYMORPHISM
	polymorphism: situasi dimana member function class turunan menimpa member function class parent

	class Ortu {
		public:
			string cetakOrtu(){
				return "Ini kelas orang tua";
			}
	};

	class Anak: public Ortu{
		public:
			string cetakOrtu(){
				return "Ini kelas anak";
			}
	};

	int main(){
		Anak objAnak;
		cout << objAnak.cetakOrtu() << endl;

		return 0;
	}

I. FILES
	files: menuliskan file secara terpisah dengan menambahkan library
	- ofstream: menulis file
	- ifstream: membaca file
	- fstream: keduanya (menulis dan membaca)

J. EXCEPTIONS
	exceptions: menangani kondisi error agar program tetap berjalan
	Contoh program:

	int pembagian(int atas, int  bawah){
		if(bawah == 0){
			throw "Error: Pembagi nol";
		}
		return atas/bawah;
	}

	int main(){
		int atas, bawah, hasil;

		while(true){
			cout << "Masukkan angka: ";
			cin >> atas;
			cout << "Masukkan angka: ";
			cin >> bawah;
			
			try{
				c = pembagian (atas, bawah);
				cout << c << endl;
			} catch (const char *e){
				cout << e << endl;
			}			
		}

		return 0;
	}
