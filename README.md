# Restaurant-Billing-Project
While using this management system, you can easily select the order from the given list of cuisines and calculate total bill of the customer. All you need to do is just select the item and fill up the blank boxes with item quantities. The program will display your total bill. 


print("Welcome to MyHotel")
menu()

def menu():
    print("Veg      : 1")
    print("Non-Veg  : 2")
    print("Desserts : 4")
    print("Bill     : 3")
    select=int(input("Enter your choice : "))
    if(select==1):
        print("    --------VEG-------")
        veg()
    elif(select==2):
        print("    ------NON VEG-----")
        nonveg()
    elif(select==4):
        print("    ------DESSERT-----")
        dessert()
    elif(select==3):
        bill()
    else:
        print("invalid selection")
        menu()
    

def veg():
    print("1) Idli          50 Rs")
    print("2) Dosa          70 Rs")
    opt=int(input("Select item to order"))
    if(opt==1):
        iqty=int(input("No.of plates :"))
        TotalIdliQuantity(iqty)
    elif(opt==2):
        dqty=int(input("No.of plates :"))
        TotalDosaQuantity(dqty)
    else:
        print("invalid selection")
        veg()

totalIdli = 0
def TotalIdliQuantity(iqty):
    global totalIdli
    totalIdli = totalIdli + iqty   
    menu()

def idlicount():
    return totalIdli

def idliprice():
    return 50

def idliname():
    return "idli" 

def ibill():
    print(idliname(),"     ", idlicount(),"     ", idliprice(),"      ", idlicount()*idliprice())

totalDosa = 0
def TotalDosaQuantity(dqty):
    global totalDosa
    totalDosa = totalDosa + dqty   
    menu()

def dosacount():
    return totalDosa

def dosaprice():
    return 70

def dosaname():
    return "Dosa" 

def dbill():
    print(dosaname(),"       " ,  dosacount(),"       " ,  dosaprice(),"       " ,  dosacount()*dosaprice())

def nonveg():
    print("1) Tandoori      150 Rs")
    print("2) Biryani       120 Rs")
    opt=int(input("Select item to order"))
    if(opt==1):
        tqty=int(input("Enter no. of plates : "))
        TotalTandooriQty(tqty)
    elif(opt==2):
        bqty=int(input("Enter no. of plates : "))
        TotalBiryaniQty(bqty)
    else:
        print("invalid selection")
        nonveg()

totaltandoori=0
def TotalTandooriQty(tqty):
    global totaltandoori
    totaltandoori=totaltandoori+tqty
    menu()
    
def tandooricount():
    return totaltandoori

def tandooriprice():
    return 150

def tandooriname():
    return "Tandoori"

def tbill():
    print(tandooriname(),"       ", tandooricount(),"       " , tandooriprice(),"       " , tandooricount()*tandooriprice())

totalBiryani=0
def TotalBiryaniQty(bqty):
    global totalBiryani
    totalBiryani=totalBiryani+bqty
    menu()
    
def biryanicount():
    return totalBiryani

def biryaniprice():
    return 120

def biryaniname():
    return "Biryani"
    

def bbill():
    print(biryaniname(),"       " , biryanicount(),"       "     ,biryaniprice(),"       "       ,biryanicount()*biryaniprice())

def dessert():
    print("1) Rasgulla         12 Rs")
    print("2) Gulabjamun       15 Rs")
    opt=int(input("Select item to order"))
    if(opt==1):
        rqty=int(input("Enter no. of pieces : "))
        TotalRasgullaQty(rqty)
    elif(opt==2):
        gqty=int(input("Enter no. of pieces : "))
        TotalGulabQty(gqty)
    else:
        print("invalid selection")
        dessert()

totalrasgulla=0
def TotalRasgullaQty(rqty):
    global totalrasgulla
    totalrasgulla=totalrasgulla+rqty
    menu()
    
def rasgullacount():
    return totalrasgulla

def rasgullaprice():
    return 12

def rasgullaname():
    return "Rasgulla"

totalgulab=0
def TotalGulabQty(gqty):
    global totalgulab
    totalgulab=totalgulab+gqty
    menu()
    
def gulabcount():
    return totalgulab

def gulabprice():
    return 15

def gulabname():
    return "Gulabjamun"

def bill():
    print("-------------------BILL--------------------")
    print("Name     Qty     Price    Amount")
    if(idlicount() > 0):
        print(idliname()    ,"     ",idlicount()    ,"     ", idliprice()    ,"     ",idlicount()*idliprice())
    if(dosacount() > 0):
        print(dosaname()    ,"     ",dosacount()    ,"     ",  dosaprice()   ,"     ",dosacount()*dosaprice())
    if(tandooricount() > 0):
        print(tandooriname()," ",tandooricount(),"    ", tandooriprice(),"     ",tandooricount()*tandooriprice())
    if(biryanicount() > 0):
        print(biryaniname() ,"  ",biryanicount() ,"    ",biryaniprice()  ,"     " ,biryanicount()*biryaniprice())
    if(rasgullacount() > 0):
        print(rasgullaname(),"  ",rasgullacount(),"    ",rasgullaprice() ,"     " ,rasgullacount()*rasgullaprice())
    if(gulabcount()>0):
        print(gulabname() ,"    ",gulabcount()   ,"    ",gulabprice(), "      ", gulabcount()*gulabprice())
    print("-------------------------------------------")    
    TotalAmount()

def TotalAmount():
    TotalAmount=idlicount()*idliprice() + dosacount()*dosaprice() + tandooricount()*tandooriprice() + biryanicount()*biryaniprice()+rasgullacount()*rasgullaprice()+gulabcount()*gulabprice()
    print("          Total Amount : Rs",TotalAmount)
    day=str(input("Enter day : "))
    if(day=="wed" or day=="fri"):
        Discount=(15/100)*TotalAmount
        FinalAmount=TotalAmount-Discount
        print("Congratulations ...!!! OFFER APPLIED..")
        print("   Discount (15%) = (-)Rs.",Discount)
        print("Total Amount After Discount : Rs. ",FinalAmount)
        print("------------------------------------")
        print("Thanks for ordering..")
    else:
        print("No Discount Today..")
        print("Thank you for ordering..")
