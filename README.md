#定义顺序表
class SeqList:
    def __init__(L):
        L.max=8
        L.num=0
        L.elems=[None]*L.max
        

       

    #判断是否为空
    def is_empty(L):
        if L.num==0:
            print("顺序表为空")
        else:
            return
        




    #输出顺序表所有元素
    def print_list(L):
        p=L.elems
        if L.is_empty():
            print("顺序表为空")
        print("顺序表:",end=" ")
        print(p)




    #尾端插入
    def insert_tail(L,x):
        if L.num==L.max:
            raise BufferError
        L.elems[L.num]=x
        L.num+=1

        

    #删除第i个元素
    def pop(L,i):
        if 0<i and i<L.num:
            for n in range(i,L.num):
                L.elems[n-1]=L.elems[n]
            L.elems[L.num-1]=None
        L.num -=1



    #顺序表的排序
    def sort(L):
        if L.is_empty():
            return
        crt=1
        while L.elems[crt] is not None:
            for i in range(crt):
                while L.elems[i]>L.elems[crt]:
                    y=L.elems[i]
                    L.elems[i]=L.elems[crt]
                    L.elems[crt]=y
            crt+=1
                
        
        







#================菜单主程序===================
if __name__=="__main__":
    link=SeqList()
#菜单页面
while True:
    print("\n==========顺序表==========")
    print("1.判断表是否为空")
    print("2.尾端插入")
    print("3.删除第i个元素")
    print("4.输出顺序表所有元素")
    print("5.顺序表的排序")
    


    #选择菜单
    choice=input("请输入你的选项(0-5):")
    #判断选择
    if choice=="1":
        link.is_empty()

    if choice=="2":
        x=int(input("请输入x的值:"))
        link.insert_tail(x)
        link.print_list()

    if choice=="3":
        i=int(input("请输入想删除的i个位置元素:"))
        link.pop(i)
        link.print_list()

    if choice=="4":
        link.print_list()

    if choice=="5":
        link.sort()
        link.print_list()# -
顺序表练习
