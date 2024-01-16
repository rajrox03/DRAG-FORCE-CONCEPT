"""
Program to calculate drag force
BY: Raj Aryan
"""
# Import module for plotting
import matplotlib.pyplot as plt

# Functions
def drag_force(c_d,A,d,v):
    """
    Calculate drag force given c_d,A,d,v:
        d -> density of fluid
        A   -> Frontal area
        c_d -> Drag coefficient
        v   -> Velocity of bicycle
    """
    return 0.5*c_d*d*A*v**2

def plotDragForceVelocity(dragForce,v):
    """
    Plots drag force v/s velocity
    """
    plt.plot(v,dragForce,'*-')
    plt.xlabel("Velocity (m/s)")
    plt.ylabel("Drag force (N)")
    plt.title("Drag force v/s Velocity plot")
    
    # Show the plot
    plt.show()

def plotDragForceCd():
    """
    Plots drag force v/s drag coefficient
    """
    # Frontal area (m^2)
    A = 0.1
    # Density (kg/m^3)
    d = 1.2
    # Velocity (m/s)
    v = 5
    # Drag coefficient for different figures
    cd = {
          "Flat plate"   : 1.28,
          "Prism"        : 1.14,
          "Bullet"       : 0.295,
          "Sphere"       : 0.47,
          "hemispherical parachute": 1.33,
          "Half sphere"  : 0.42,
          "Cone"         : 0.50,
          "Cube"         : 1.05,
          "Angled cube"  : 0.80,
          "Long cylinder": 0.82,
          "Pac-car"      : 0.075,
          "Milan SL"     : 0.076,
          "BMW 320D"     : 0.23,
          "Porsche 911 Gt 3RS": 0.34
          }
    dragForces = {}
    for i in cd.keys():
        dragForces[i] = drag_force(cd[i],A,d,v)
    # Plot results
    for i in cd.keys():
        plt.plot(cd[i],dragForces[i],'*',label=i)
    plt.legend(loc='upper right')
    plt.xlabel("Drag coefficient")
    plt.ylabel("Drag force")
    plt.title("Drag force v/s drag coefficient (5 m/s)")
    plt.show()

def plotResultsForBicycle():
    """
    Plot drag force v/s velocity for bicycle
    """
    # Drag coefficient
    c_d = 0.8
    # Frontal area (m^2)
    A = 0.1
    # Density (kg/m^3)
    d = 1.2
    # Bicycle velocity (m/s)
    # Velocity is varying from 1 to 10 m/s in steps of 0.1 m/s
    v = [i/10 for i in range(10,100,1)]
    # Drag force values
    dragForce = [drag_force(c_d,A,d,velocity) for velocity in v]
    plotDragForceVelocity(dragForce,v)

def main():
    plt.figure("Drag coefficient v/s velocity")
    plotResultsForBicycle()
    plt.figure("Drag coefficient v/s drag force")
    plotDragForceCd()

if _name_ == "_main_":
    main()
