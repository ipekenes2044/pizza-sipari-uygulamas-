import tkinter as tk

form=tk.Tk()
form.geometry('500x500+400+100')
form.title('Pizza Sipariş Programı')
baslik=tk.Label(text='Pizza Sipariş Programına Hoşgeldiniz',fg='black',bg='green',font='Times 17 italic').pack()

entr=tk.StringVar()
entr1=tk.StringVar()
llb_ad=tk.Label(form,text='Ad-Soyad:',bg='pink',font='Times 12 italic').place(x=10,y=40)
llb_boyut=tk.Label(form,text='Boyut:',bg='pink',font='Times 12 italic').place(x=10,y=70)
llb_icindekiler=tk.Label(form,text='İçindekiler:',bg='pink',font='Times 12 italic').place(x=10,y=100)
llb_adres=tk.Label(form,text='Adres:',bg='pink',font='Times 12 italic').place(x=10,y=130)

# 2. kısım
entry=tk.Entry(textvariable=entr).place(x=100,y=40)
entry_adres=tk.Entry(textvariable=entr1).place(x=100,y=130)

boyut=tk.StringVar()

rdbuton_kücük=tk.Radiobutton(form,text='Küçük Boy',activebackground='green',value='Küçük Boy',variable=boyut).place(x=100,y=70)
rdbuton_orta=tk.Radiobutton(form,text='Orta Boy',activebackground='green',value='Orta Boy',variable=boyut).place(x=160,y=70)
rdbuton_büyük=tk.Radiobutton(form,text='Büyük Boy',activebackground='green',value='Büyük Boy',variable=boyut).place(x=240,y=70)

deger1=tk.StringVar()
deger2=tk.StringVar()
deger3=tk.StringVar()

Check1=tk.Checkbutton(form,text='Sucuklu',variable=deger1,onvalue='Sucuklu',offvalue='').place(x=100,y=100)
Check2=tk.Checkbutton(form,text='Mısır',variable=deger2,onvalue='Mısır',offvalue='').place(x=180,y=100)
Check3=tk.Checkbutton(form,text='Acılı sos',variable=deger3,onvalue='Acılı sos',offvalue='').place(x=240,y=100)

# 3. kısım
def siparişver():
    label_bilgi=tk.Label(form,text='Sipariş Bilgileri',bg='green',font='Times 16 italic').place(x=50,y=240)
    llb_ad=tk.Label(form,text='Ad-Soyad:',bg='pink',font='Times 12 italic').place(x=10,y=270)
    llb_boyut=tk.Label(form,text='Boyut:',bg='pink',font='Times 12 italic').place(x=10,y=300)
    llb_icindekiler=tk.Label(form,text='İçindekiler:',bg='pink',font='Times 12 italic').place(x=10,y=330)
    llb_adres=tk.Label(form,text='Adres:',bg='pink',font='Times 12 italic').place(x=10,y=360)

    llb_ad1=tk.Label(form,text=entr.get(),font='Times 12 italic').place(x=100,y=270)
    llb_boyut1=tk.Label(form,text=boyut.get(),font='Times 12 italic').place(x=100,y=300)

    # Seçilen içindekileri al
    icindekiler = ', '.join([deger for deger in [deger1.get(), deger2.get(), deger3.get()] if deger])
    
    llb_icindekiler1 = tk.Label(form, text=icindekiler,  font='Times 12 italic').place(x=100,y=330)

    llb_adres1=tk.Label(form,text=entr1.get(),font='Times 12 italic').place(x=100,y=360)

def iptalet():
    form.quit()

sipariş=tk.Button(form,text='Sipariş Ver',activebackground='green',command=siparişver).place(x=130,y=160)

iptal=tk.Button(form,text='İptal et',activebackground='red',command=iptalet).place(x=220,y=160)

form.mainloop()
