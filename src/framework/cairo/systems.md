## Systems

Systems represent functions that operate on the world state. They take input from the user, retrieve the current state from the world, compute a state transition, and apply it. Each system has a single entry point, the execute function. To streamline interaction with the world, systems can utilize
commands.

```rust,ignore
#[system]
mod Spawn {
    use array::ArrayTrait;
    use traits::Into;

    use dojo::world::Context;
    use dojo_examples::components::Position;
    use dojo_examples::components::Moves;

    fn execute(ctx: Context) {
        set !(
            ctx.world, ctx.origin.into(), (Moves { remaining: 10 }, Position { x: 0, y: 0 }, )
        );
        return ();
    }
}
```
