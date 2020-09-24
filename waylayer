# -*- coding: utf-8 -*-
import sqlite3 as sql 
import datetime
import calendar


running = True
while running:
     print("1 - Добавление\n2 - получение")
     choice = int(input(">"))
     con = sql.connect('Base.db')
     with con:
          cur = con.cursor()
          cur.execute("CREATE TABLE IF NOT EXISTS 'Base' (t INTEGER, god INTEGER, eventu TEXT, deskription TEXT) ")
          if choice == 1:
               t = int(input("Введите месяц\n"))
               god = int(input("Введите год\n"))
               eventu = input("Введите событие\n>") 
               deskription = input ("Введите описание\n>")
               cur.execute( f"INSERT INTO 'Base' VALUES ( '{t}','{god}', '{eventu}' , '{deskription}')")
          elif choice == 2:
               cur.execute("SELECT * FROM 'Base' ")
               rows = cur.fetchall()
               for row in rows:
                    print(row[0], row[1],row[2], row[3])                   
          else:
               print ("Вы ошиблись")    

     if input("Хотите продолжить? (y/N)")!= "y":
          break
     print("Добра!")
con.commit()
cur.close()
