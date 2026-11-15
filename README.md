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

AZ::Component
- Init
- Activate
- Deactivate
- Reflect

AZ::Module
- m_descriptors
- GetRequiredSystemComponents

AZ::EBusTraits
- your own bus config : HandlerPolicy, AddressPolicy

EBus<...>::Handler
- request or notification


## Macros
AZ_RTTI

AZ_COMPONENT_DECL

AZ_COMPONENT_IMPL

## QuickShort
- AZ::Component - behavior in the scene
- AZ::Module - your own gem
- AZ::Data::AssetData - your own asset type
- AZ::RPI::FeatureProcessor - renderer extension
- EditorComponentBase - Component as viewed in the Editor
- EBus / AZ::Interface - when you need to "talk" with a component

## Components
can either derive from 
- SystemComponent ex. Module::GetRequiredSystemComponent
- EntityComponent ex. TransformComponent, MeshComponent

## Layer Below Components
- Feature Processors
      - ex. MeshFeatureProcessorInterface
- Interfaces
      - ex. AZ::Interface<T>, WorldInterface
- Subsystems
      - ex. AZ::Data::AssetManager

## Bus
- ...RequestBus - You call, something responds
- ...NotificationBus - something calls you
- Broadcast | BroadcastResult - global without | with result
- Event | EventResult - certain adress without | with result
- HandlerPolicy::Single - single listener
- HandlerPolicy::Multiple - multiple listeners

Graph: </br>

EBus
|_____adress
            |
            |____handler

## Miscellaneous 
- using Event = typename Impl::Event
- using Policy = typename Traits::template Policy<Type>
