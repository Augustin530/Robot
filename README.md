class Robot:
    def __init__(self, name, battery_level=100):
        self.name = name  # 機器人名稱
        self.battery_level = battery_level  # 機器人電池電量
        self.tasks = []  # 需要完成的任務列表

    def charge(self):
        self.battery_level = 100
        print(f"{self.name} is fully charged.")

    def add_task(self, task):
        self.tasks.append(task)
        print(f"Task '{task}' added to {self.name}'s task list.")

    def perform_task(self):
        if self.battery_level > 10 and self.tasks:
            task = self.tasks.pop(0)
            self.battery_level -= 10  # 每完成一個任務消耗10%的電量
            print(f"{self.name} is performing task: {task}. Battery level: {self.battery_level}%")
        else:
            print(f"{self.name} needs to recharge or there are no tasks.")

    def status(self):
        print(f"{self.name}'s battery level is {self.battery_level}%. Tasks remaining: {len(self.tasks)}.")

# 創建一個 Robot 物件並進行操作
robot = Robot("RoboHelper")
robot.add_task("Clean the house")
robot.add_task("Cook dinner")
robot.status()
robot.perform_task()
robot.perform_task()
robot.status()
robot.charge()
robot.status()
# Robot
