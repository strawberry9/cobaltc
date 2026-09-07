module example;

import io { print, println };

const i32 limit = 3;

enum State
{
    Ready,
    Running,
    Finished
}

struct Counter
{
    i32 value;
}

fn Counter::increment(mut Counter* counter)
{
    counter->value = counter->value + 1;
}

fn describe(State state) : String
{
    return match state
    {
        Ready    => "ready",
        Running  => "running",
        Finished => "finished"
    };
}

fn main()
{
    mut Counter counter = Counter
    {
        value = 0
    };

    println(describe(Ready)); // ready

    while (counter.value < limit)
    {
        // Temporary mutable borrow of counter for the duration of the call.
        Counter::increment(&mut counter);

        print("count = ");
        println(counter.value);
    }

    println(describe(Finished)); // finished
}
