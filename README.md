# Yet Another SCIntillation detector driver

A set of PCB designs to drive a PMT-based scintillation detector.  
Never got to finish it - the hardware is more or less done and largely tested, but failed to force myself to write the software/firmware.

## Power supply

 * A PMT needs around -1000V to work.
 * The logic stuff needs 5V.
 * The amplifier needs +5V and -5V.

This is a little brick that produces all of the above from 12V, using off-the-shelf converters to get +-5V and isolated 12V, boosting the isolated 12V to 250V, and voltage multiplying the 250V to 1000V.

## Amplifier

Takes the pulses from the PMT, amplifies and inverts them.  
I think i replaced MCP6021 with OPA172, for voltage limit reasons.

## ADC

An FPGA module with an ADC attached to it.  
Takes the analog output of the amplifier, digitizes it, processes/detects peaks, and saves it on a microsd card.  
The sync output is there to synchronize timings between several boards, i.e. for muon detection.

## Blank / FEU-85 / FEU-35

PMT boards, with amplifier mount point and resistor divider ladder.  
Pinouts for common ФЭУ-85 and ФЭУ-35 PMT tubes, as well as a blank one intended for an already-populated PMT module.
