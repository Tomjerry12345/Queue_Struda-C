#include<iostream>
#define MAX 20
using namespace std;

int data;
struct antrian{
	int depan,belakang,data[MAX],tmp;
}q;
bool penuh(){
	return q.belakang == MAX;
}
bool kosong(){
	return q.belakang == 0;
}
void cetakqueue(){
	if(kosong()){
		cout<<"Antrian Kosong"<<endl;
	}
	else{
		cout<<"QUEUE : \n";
		for(int i=q.depan;i<=q.belakang-1;i++){
			for(int j=q.depan;j<i;j++){
				if(q.data[i]<=q.data[j]){
					q.tmp=q.data[i];
					q.data[i]=q.data[j];
					q.data[j]=q.tmp;				
				}
			}
		}
		for(int i = q.depan;i<q.belakang;i++){
			cout<<q.data[i]<<((q.belakang-1 == i) ? "" : ",");
			cout<<endl;
		}
	}
}

void hapus()
{
	q.belakang = 0;
}

void enqueue(){
	if(penuh()){
		cout<<"Antrian Penuh !"<<endl;
	}
	else{
		cout<<"Masukkan Data : ";cin>>data;
		q.data[q.belakang] = data;
		q.belakang++;
		cout<<"Data ditambahkan\n";
	}
}
void dequeue(){
	if(kosong()){
		cout<<"Antrian masih kosong!"<<endl;
	}
	else{
		cout<<"Mangambil Data : "<<data<<"\"..."<<endl;
		for(int i = data; i<q.belakang;i++)
			q.data[i] = q.data[i+1];
			q.belakang--;
	}
}

int main(){
	int pilih;
	do{
		system("cls");
		cetakqueue();
		cout<<"==============================\n"
			<<"        MENU PILIHAN          \n"
			<<"==============================\n"
			<<" [1] Masukkan Antrian \n"
			<<" [2] Kurangi Antrian \n"
			<<" [3] Hapus \n"
			<<" [4] Keluar \n"
			<<"==============================\n"
			<<"Masukkan pilihan : "; cin>>pilih;
		switch(pilih){
			case 1 :
				enqueue();
				break;
			case 2 :
				dequeue();
				break;
			case 3 :
				hapus();
				break;
			default:
				cout<<"Pilihan tidak tersedia";
				break;
		}
	}while(pilih != 4);
	return 0;
}
