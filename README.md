Список команд для выполнения Д/З 19.2 - "QuerySet запросы в базу данных":

(.venv) PS C:\Users\User\PycharmProjects\pythonProject5> cd module_19                       
(.venv) PS C:\Users\User\PycharmProjects\pythonProject5\module_19> python manage.py shell
>>> from task1.models import Buyer, Game
>>> buyer1 = Buyer.objects.create(name='Alex', balance = 2000,  age=17)
>>> buyer2 = Buyer.objects.create(name='Oleg', balance = 2500,  age=20) 
>>> buyer3 = Buyer.objects.create(name='Ilya', balance = 3000,  age=22) 
>>> game1 = Game.objects.create(title='Cyberpunk 2077', cost = 2600,  size=50, description='Game of the year', age_limited=False) 
>>> game2 = Game.objects.create(title='Mario', cost = 200,  size=0.5, description='Old Game', age_limited=True)                   
>>> game3 = Game.objects.create(title='Hitman', cost = 150,  size=40, description='Who kills Mark?', age_limited=False) 
>>> Game.objects.filter(age_limited=False).update(age_limited=True)                                                               
2
>>> Game.objects.filter(cost=200).update(age_limited=False)         
1
>>> Game.objects.get(cost=2600).buyer.set([buyer3]) 
>>> game2.buyer.set([buyer1, buyer2, buyer3])       
>>> Game.objects.get(id=3).buyer.set([buyer2, buyer3])             
>>>
