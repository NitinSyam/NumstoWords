a = ['',
    'one', 'two', 'three', 'four', 'five', 'six', 'seven', 'eight', 'nine', 'ten', 
    'eleven', 'twelve', 'thirteen', 'fourteen', 'fifteen', 'sixteen', 'seventeen',
    'eighteen', 'nineteen'
]
b = ['', '', 'twenty', 'thirty', 'forty', 'fifty', 'sixty', 'seventy', 'eighty', 'ninety', 'hundred']
money = (input("Enter the money in numbers: "))
pindex = money.find('.')
if pindex>=0:
    intmoney = int(money[0:pindex])
    decmoney = int(money[pindex+1:len(money)])
else:
    intmoney = int(money)
    decmoney=0
def paise(decmoney):
    dmoney = str(decmoney)
    if(decmoney<20):
        return a[decmoney]
    elif(decmoney<100):
        return b[int(dmoney[0])] +a[int(dmoney[1])]
def nopoint(intmoney):
    money = str(intmoney)
    if(intmoney<20):
        return a[intmoney]
    elif(intmoney<100):
        return (b[int(money[0])] + " " + a[int(money[1])])
    elif(intmoney<1000):
        money1 = int(money[1:3])
        if (money1==0):
            return (a[int(money[0])]+" hundred")
        elif (money1<20):
            return (a[int(money[0])]+" hundred and " + a[money1])
        else:
            return (a[int(money[0])]+" hundred and " +b[int(money[1])] + " " + a[int(money[2])])
    elif(intmoney<10000):
        money2 = int(money[2:4])
        money3 = int(money[1:4])
        if (money3==0):
            return (a[int(money[0])]+" thousand")
        elif (money2==0):
            return (a[int(money[0])]+" thousand "+a[int(money[1])]+" hundred")
        elif (int(money[1])==0):
            return (a[int(money[0])]+" thousand "+b[int(money[2])] + " " + a[int(money[3])])
        elif (money2<20):
            if(int(money[1:3])==00):
                return (a[int(money[0])]+" thousand "+a[money2])
            else:
                return (a[int(money[0])]+" thousand "+a[int(money[1])]+" hundred and "+
                a[money2])
        else:
            return (a[int(money[0])]+" thousand "+a[int(money[1])]+" hundred and "+
                b[int(money[2])] + " " + a[int(money[3])])
if decmoney>0:
    print("Rupees "+nopoint(intmoney)+" and "+paise(decmoney)+" paise only")
else:
    print("Rupees "+nopoint(intmoney)+" only")
