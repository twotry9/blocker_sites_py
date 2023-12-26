HOST="C:\Windows\System32\drivers\etc\hosts"
REDIRECT_IP='127.0.0.1'


def block_website(websites):
    '''Blocks the all the websites which are mentioned in the list'''

    if type(websites) != type([]):
        raise TypeError('Paramerter websites expects a list')

    with open(HOST,'r+') as f:
        content=f.read()

        for website in websites:

            if website not in content:
                f.write("{} {}\n".format(REDIRECT_IP,website))

    f.close()
    print('Заблокировано !',end='\n\n')

def unblock_website(websites):
    with open(HOST,'r+') as f:
        content=f.readlines()
        f.seek(0)

        for line in content:
            if not any(website in line for website in websites):
                f.write(line)
        f.truncate()
        f.close()
    print('Разблокировано !',end='\n\n') 


if __name__=='__main__':
    while True:
        for op in ["1.Заблокировать Website","2.Разблокировать Website","3.Выход"]:
            print(op)
        option=int(input('Введите номер операции :'))

        if option==1:
            print('Вы использовали вариант 1: Заблокировать')
            print('Пожалуйста, введите названия вебстайтов для блокировки через зпятую(,)',end='\n\n')
            webpages=input('Введите название сайта, как в адресной строке :')
            webpages=webpages.split(',')
            block_website(webpages)

        elif option==2:
            print('Вы использовали вариант 2: Заблокироваать')
            print('Пожалуйста, введите названия сайтов для разблокировки через зпятую(,)',end='\n\n')
            webpages=input('Введите название сайта, как в адресной строке :')
            webpages=webpages.split(',')
            unblock_website(webpages)

        elif option==3:
            print('Выход из программы')
            break
        else:
            print('Неверная опция')
            break
