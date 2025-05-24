import tkinter as tk
from tkinter import filedialog
import pygame

pygame.mixer.init()

def muzik_sec():
    dosya_yolu = filedialog.askopenfilename(filetypes=[("Ses Dosyaları", "*.mp3 *.wav")])
    if dosya_yolu:
        muzik_yolu.set(dosya_yolu)
        pygame.mixer.music.load(dosya_yolu)

def cal():
    pygame.mixer.music.play()

def duraklat():
    pygame.mixer.music.pause()

def devam_et():
    pygame.mixer.music.unpause()

def durdur():
    pygame.mixer.music.stop()


pencere = tk.Tk()
pencere.title("Basit Müzik Çalar")
pencere.geometry("300x200")

muzik_yolu = tk.StringVar()

tk.Button(pencere, text="Müzik Seç", command=muzik_sec).pack(pady=10)
tk.Button(pencere, text="Çal", command=cal).pack()
tk.Button(pencere, text="Duraklat", command=duraklat).pack()
tk.Button(pencere, text="Devam Et", command=devam_et).pack()
tk.Button(pencere, text="Durdur", command=durdur).pack()

pencere.mainloop()
