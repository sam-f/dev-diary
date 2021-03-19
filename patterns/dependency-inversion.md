# Dependency inversion

Imagine you have a class, Animal that takes depends on LegCounter.

```ruby
class Animal
    def legs
        LegCounter.count(self)
    end
end
```

You can invert this dependency for testing and reuse.

```ruby
class Animal
    def initialize(leg_counter: LegCounter)
        @leg_counter = leg_counter
    end

    def legs
        leg_counter.count(self)
    end
end
```

## Why is this an improvement?

Consider your tests. Instead of mocking out LegCounter.count to return something, you can pass in your own FakeLegCounter and just set the value to what you want.

You can also consider that Animal may expand to include marine animals. Leg counting may differ between different classes of animal, and so there may be a need for MarineAnimalLegCounter. When this arises, no changes need be made, rather just the class you pass into the initializer. 