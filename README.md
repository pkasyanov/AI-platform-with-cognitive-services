# AI-platform-with-cognitive-services
AI platform with cognitive services for coordinated autonomous navigation of distributed systems under electronic warfare (EW) conditions          

# Демонстрація всіх можливостей
python ground_control_center.py demo

# Інтерактивний режим для операторів
python ground_control_center.py interactive

# Програмний доступ
from ground_control_center import GroundControlCenter
gcc = GroundControlCenter()
gcc.start()

## Приклад використання

# Створення місії розвідки
mission_id = gcc.create_and_plan_mission(
    mission_type='reconnaissance',
    target_coordinates=[(100, 100, 50), (200, 200, 50)],
    drone_count=4,
    optimization_algorithm='genetic'
)

# Симуляція перед реальним виконанням
sim_id = await gcc.simulate_mission(mission_id)

# Розгортання на реальних дронах
gcc.deploy_mission(mission_id, ['drone_1', 'drone_2', 'drone_3', 'drone_4'])
