import pmpy

def createCostumers(e,c):
    while True:
        yield e.do('wait',2)
        yield e.add(c,1)
        if(c.level()==10):
            break
    
        
def serve(server,c):
    while True:
        yield server.get(c,1)
        yield server.do('serve',4)

env=pmpy.Environment()
c=pmpy.PriorityResource(env,'customer',init=0,capacity=10,print_actions=True)
e=pmpy.Entity(env,'e')
server=pmpy.Entity(env,'server')
env.process(createCostumers(e,c))
env.process(serve(server,c))
env.run()
