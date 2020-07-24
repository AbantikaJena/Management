from os import path

file=open('hotel','a')
file.close()

class Hotel:

    def __init__(self,mtableno, mitem, mno_of_plates, mrate):
        self.tableno=mtableno
        self.item=mitem
        self.no_of_plates=mno_of_plates
        self.price = mrate

    def Order_Entry(self):
        with open('hotel','a+') as hotel:
            hotel.write(self.tableno+'#'+self.item+'#'+self.no_of_plates+'#'+self.price+'\n')


    def Print_Bill(self):
        tablenum=int(input('Enter the table number: '))
        print('{:^103s}'.format('HOTEL PRINCE'))
        print('{:^103s}'.format('CC BHILAI'))

        with open('hotel','r') as hotel:
            tamount=0

            print('TABLE NO.: {:^6d}'.format(tablenum))
            print('-'*103)
            print('| {:^30s} | {:^20s} | {:^20s} | {:^20s} |'.format('ITEM NAME','NO OF PLATES','RATE','AMOUNT'))
            print('-'*103)

            for i in hotel:
                data=i.rstrip('\n').split('#')

                if int(data[0])==tablenum:
                    tamount+=int(data[2])*int(data[3])
                    print('| {:^30s} | {:>20d} | {:>20d} | {:>20d} |'.format(data[1],int(data[2]),int(data[3]),int(data[2])*int(data[3])))
            print('-'*103)

            print('\n{:>95s}: {:<6d}'.format('TOTAL AMOUNT',tamount))

menu='''
    1: Enter Data
    2: View Data
    3: Quit
  '''


hotel=Hotel('','','','')
while True:
    print(menu)
    option=int(input('Choose 1, 2 or 3: '))

    if option==1:
        print()
        tableno=input('Enter table number: ')
        item=input('Enter item name: ')
        plates=input('Enter the number of plates ordered: ')
        rate=input('Enter the rate: ')

        hotel=Hotel(tableno,item,plates,rate)
        hotel.Order_Entry()


    elif option==2:
        size=path.getsize('hotel')

        if size==0:
            print('\nThere is no data in it. Use option 1')

        else:
            print()
            hotel.Print_Bill()
            print()

    else:
        break
