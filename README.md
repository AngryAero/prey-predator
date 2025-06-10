# Prey-Predator Ecosystems - Simulating the Snowshoe Hare & Canada Lynx

## Agents

### Hares (Preys)

<p>The ecosystem has two agents that interact with each other and the environment, attempting to simulate the classic relationship between the Snowshoe Hare and the Canada Lynx.</p>

<li>Represented as white ‘turtles’ </li>
<li>Possesses an <strong>energy</strong> level, initially set to a random value (0 to 99)</li>
<li>Moves randomly across the environment</li>
<li>Each step costs 1 energy </li>
<li>Energy is replenished by eating green grass, equal to <strong>grass-energy-gain</strong></li>
<li>Dies when energy level reaches 0</li>
<li>Has a chance of reproducing when energy is above the <strong>reproduction-energy-threshold</strong>, costing energy</li>
<li> Newly born hares start with an energy level set to <strong>reproduction-energy-cost</strong> * <strong>reproduction-efficiency</strong> </li>

### Lynxes (Predators)

<li>Represented as red ‘turtles’ </li>
<li>Possesses an <strong>energy</strong> level, initially set to a random value (0 to 99)</li>
<li>Moves randomly across the environment</li>
<li>Each step costs 1 energy </li>
<li>Energy is replenished by eating hares, equal to <strong>prey-energy-gain</strong></li>
<li>Dies when energy level reaches 0</li>
<li>Has a chance of reproducing when energy is above the <strong>reproduction-energy-threshold</strong>, costing energy</li>
<li> Newly born hares start with an energy level set to <strong>reproduction-energy-cost</strong> * <strong>reproduction-efficiency</strong> </li>

## Environment

### Land

<p>The environment is set on a spatial grid of patches.</p>

<li>Can either be <strong>green</strong> (has grass and can be eaten by hares) or <strong>brown</strong> (no grass)</li>
<li>Possesses a <strong>growth level</strong></li>
<li>Growth level of each patch has a chance of incrementing each tick, determined by <strong>grass-regrowth-chance</strong></li>
<li>Once a brown patch’s growth level is greater than a set value (referred to as the <strong>regrowth threshold</strong>), the patch will turn green again and can be eaten again</li>
<li>The time it takes for grass to regrow can be set at a static level, or can be toggled into a <strong>seasonal mode</strong>, where the threshold <strong>oscillates between long and short times</strong>, simulating summer and winter months. The length and magnitude of each season are determined by the season-speed and season-amplitude parameters, respectively.</li>

### Default Parameters

| **Category**              | **Setting**                   | **Value**    |
| ------------------------- | ----------------------------- | ------------ |
| **Initialization**        | initial-hares                 | 100          |
|                           | initial-lynxes                | 100          |
| **Grass Settings**        | grass-regrowth-time-base      | 30           |
|                           | grass-regrowth-chance         | 66           |
| **Energy Gain Settings**  | grass-energy-gain             | 10           |
|                           | prey-energy-gain              | 25           |
| **Reproduction Settings** | reproduction-chance           | 20           |
|                           | reproduction-energy-threshold | 75           |
|                           | reproduction-energy-cost      | 40           |
|                           | reproduction-efficiency       | 0.75         |
| **Season Settings**       | is-seasonal                   | Off (toggle) |
|                           | season-amplitude              | 10.0         |
|                           | season-speed                  | 0.15         |
| **Simulation Control**    | max-ticks                     | 500          |
