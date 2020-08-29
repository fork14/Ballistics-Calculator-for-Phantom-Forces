Source so you know this aint a virus

#u = max dmg
#v = min dmg
#a = max dmg range
#b = min dmg range
#L = specific damage
#R = specific range
#M = damage multiplier
#ROC is (v-u)(b-a)
#(R-a)(v-u)/(b-a) + u = L is function for damage at specific range
#(u-L)(b-a)/(u-v) + a = R is for finding range at specific damage
lop = True
while lop == True:
  ch = input("Range or Damage?")
  ch.lower()
  if ch == "range":
    u = float(input("Max Damage: "))
    v = float(input("Min Damage: "))
    a = float(input("Max Damage Distance (The LOWER Stud Value): "))
    b = float(input("Min Damage Distance (The HIGHER Stud Value): "))
    L = float(input("Damage: "))
    M = float(input("Damage Multiplier: "))
    u = M*u
    v = M*v

    if L>u:
      L=u
    elif L<v:
      L=v
      
    R = (u-L)*(b-a)/(u-v)+a

    print(L, "Damage at", R, "Studs")
    lop = False
    input()
    
  elif ch =="damage":
    u = float(input("Max Damage: "))
    u = float(input("Max Damage: "))
    v = float(input("Min Damage: "))
    a = float(input("Max Damage Distance (The LOWER Stud Value): "))
    b = float(input("Min Damage Distance (The HIGHER Stud Value): "))
    R = float(input("Range: "))
    M = float(input("Damage Multiplier: "))
    L = (R-a)*(v-u)/(b-a)+u

    if R < a:
      L = M*u
    elif R > b:
      L = M*v
    else:
      L = M*L
      
    print(L, "Damage at", R, "Studs")
    lop = False
    input()
    
  else:
    print("?")
