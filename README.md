# sec2 Drone Transportation

# System Setup and Testing Instructions

## Installing, Setting Up, and Starting Containers

### Clone the code for the system
```
git clone https://gitlab.tamk.cloud/sw-architectures-and-design-2023-rishu-kumar/final-sw-architecture-project-work.git
```

Run it using Spring Boot

## Testing Instructions

## Console for HiveMQ

```
/opt/homebrew/opt/activemq/bin/activemq console

```

## Pizza Store
### Place Order

```
curl -X POST -H "Content-Type: application/json" -d '{"Order_id":"2", "Pizza_name":"Margherita", "size": "big"}' http://localhost:8481/pizza/orders
```

### See Order Details

```
curl http://localhost:8481/pizza/orders
```

### Cancel Order

```
curl -X DELETE http://localhost:8481/pizza/orders/1
```

### Message from Control Centre and Drone Unit

```
curl http://localhost:8481/pizza/send_drone/1
```

## Control Center

### Assign Drones

```
curl -X POST -H "Content-Type: application/json" -d '{"id":"1", "name":"droneverse", "capacity": 456}' http://localhost:8482/control/drones/
```

### Drones Details

```
curl http://localhost:8482/control/drones/
```

### Update Drone Details

```
curl -X PUT -H "Content-Type: application/json" -d '{"id":"4", "name":"drone4", "capacity": 439}' http://localhost:8482/control/drones/
```

### Remove Drone

```
curl -X DELETE http://localhost:8482/control/drones/1
```

### Fleet Details

```
curl http://localhost:8312/fleet/v1/flights
```

### Monitoring Details

```
curl http://localhost:8312/fleet/v1/flights
```

## Drone Unit

### Drone Assignment

```
curl -X POST http://localhost:8484/drone/v1/assignments/ready
```

### Drone Details

```
curl http://localhost:8484/drone/v1/assignments/ready
```