# Geothermal Economics
Based on *Geothermal Handbook (ESMAP 2012)*

## Geothermal Energy

### High Temperature Field

- Heat source
	- magma or hot rock
- Convective system
	- heat convects down from sides, upwards over heat source

### Location

**High-temperature** geothermal found near:
- volcanic areas
	- often close to tectonic plate boundaries
	- may not be easily accessible, populated area

### Types and Uses

| Resource Type         | Goegraphical/Geological Location                           | Use/Technology                                                                    |
| --------------------- | ---------------------------------------------------------- | --------------------------------------------------------------------------------- |
| High: &g;200&#176C    | Boundaries of tectonic plates, hot spots, volcanic areas   | Power generation: conventional steam, flash, double flash, dry steam technology   |
| Medium: 150-200&#176C | Sedimentary geology or adjacent to high temp. resources    | Power gen. w/ binary power plants                                                 |
| Low: &l;150&#176C     | Exist in most countries, 150&#176C found at depth of ~5 km | Direct use (space and process heating), limited power gen. w/ binary power plants |                      |                                                            |                                                                                   |

### Pros and Cons

| Advantage                                                     | Challenge                                               |
| ------------------------------------------------------------- | ------------------------------------------------------- |
| Globally inexhaustible                                        | Locally exhaustible                                     |
| Low CO<sub>2</sub>, air pollutant emissions                   | Hydrogen sulfide (H<sub>2</sub>S) content can be high   |
| Low land requirement                                          | Often in inaccessible areas                             |
| Isolated from fuel price volatility, no need for fuel imports | Geothermal "fuel" is non-tradable, location constrained |
| Non-intermittent (strong base-load resource)                  | Limited ability to follow/respond to demand             |
| Relatively low cost per kWh                                   | High risk, investment cost, long development cycle      |
| Proven/mature technology                                      | Require sophisticated maintenance                       |
| Scalable to utility size without much land use                | Requires extensive drilling                             |

### Geothermal Development in Iceland

| Plant           | Electric Capacity |
| --------------- | ----------------- |
| 1. Bjaranarflag | 3.2 MW            |
| 2. Svartsengi   | 76.4 MW           |
| 3. Krafla       | 60 MW             |
| 4. Nesjavellir  | 120 MW            |
| 5. Husavik      | 2 MW              |
| 6. Reykjanes    | 100 MW            |
| 7. Hellishedi   | 213 MW            | 

### Power Generation Technologies

| Technology    | % of 67 TWh total |
| ------------- | ----------------- |
| Single flash  | 42                |
| Dry steam     | 24                |
| Double flash  | 21                |
| Binary        | 8                 |
| Back pressure | 4                 |

#### Single Flash

 - flash - drop pressure of geothermal fluid
	 - increases steam content
	 - done twice for double flash
 - separate geothermal fluid from steam before entering turbine

### Multiple Uses

Energy and waste can be used for other processes:
- fish farming
- greenhouses
- swimming pools
- crop drying

### Costs

- Power plant 35%
- Drilling 34%
- Steam collection system

Further depends on:
- Ease of business
- Availability of skilled labor
- Geology and geography

### System demand

- Total geothermal capacity should not exceed minimum demand
	- Typically not equipped to follow demand, provide base load power
	- Often given priority dispatch
		- High capacity factor, want to save resources that can be stored (hydro)
	- Workarounds
		- Interconnections (increase minimum demand)
		- Turbine bypass (wastes steam)

### Reservoir Potential and Plant Size

Build in steps:
- based on preliminary surveys and test drillings
- 30-60 MW steps, minimizes risks of
	- pressure drops
	- reservoir depletion
- Operate just initial unit at first
	- provides information about "dependable potential"
		- production that can be sustained for 100-300 years
			- overuse in short term leads to loss in future capacity

### Profit Maximization Strategy

- initially invest in capacity that exceeds "long-term sustainable" production
- allow production to taper to recharge rate if drilling extra capacity too expensive

### Modified Hotelling Model

Maximize:
$$\underbrace{\Pi}_\text{profit}=\sum_{i=1}^n(\underbrace{I(P_i,E_i)}_\text{income}-\underbrace{C_w(N_i,N_{i-1}-C_{\text{om}}(E_i,N_i))}_\text{variable costs}e^{-r(i-1)\Delta t}-\sum_{j=1}^m\underbrace{C_p(E_{pj})}_\text{construction cost}e^{-r(j-1)\Delta t_p}$$
Constraints:
$$\underbrace{S_i}_\text{current stock} = \underbrace{S_{i-1}}_\text{stock from previous time period}-\underbrace{E_i\Delta t}_\text{energy used}+\underbrace{R(S_{i-1})\Delta t}_\text{energy recharged}$$
