# O3DE_tutorial

AZ::Entity
- Get/SetId()
- Get/SetName()
- Reset()
- void Init() override
- void Activate() override
- void Deactivate() override
- bool AddComponent(Component* c)
- bool RemoveComponent(Component* c)
- GetState()
    Constructed
    Initiating -> Init
    Activating -> Active
    Deactivating -> Init
    Destroying -> Destroyed
  
