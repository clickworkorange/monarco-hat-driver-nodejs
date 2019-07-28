# monarco-hat - Node.js driver library for Monarco HAT

Compatible Monarco HAT firmware version: 2.006 and newer

### Getting started

#### Install prerequisites
Install required build-dependencies on your Raspbian running on Raspberry Pi:

```
sudo apt update
sudo apt install build-essential 
```

Install Node.js on your Raspbian running on Raspberry Pi:

```
curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -
sudo apt install -y nodejs
```

If you are interested in details, see [Installing Node.js via package manager](https://nodejs.org/en/download/package-manager/#debian-and-ubuntu-based-linux-distributions).

#### Acquiring the package

Install the package using *npm* registry:

```
npm install monarco-hat
```

If installed correctly the package is located in `./node-modules/monarco-hat/`.

### Example
The most comprehensive way how to get into using the Node.js library for Monarco HAT is to examine the **application example**, which is located in ~/node_modules/monarco-hat/index.js.

#### Running the demo example
To run the demo first change the current working directory to the location where the package is installed and then execute the example application:

```
cd ~/node_modules/monarco-hat
npm start
```

```
### Monarco HAT Node.js library demo example v1.0
Cycle interval: 50 [ms]

MONARCO SDC INIT DONE, FW=00002005, HW=00000104, CPUID=0367011264953669
DI1..4: 1111 | CNT1: 00000 | CNT2: 00000 | AIN1: 1.937 | AIN2: 5.150
DI1..4: 1110 | CNT1: 00000 | CNT2: 00001 | AIN1: 1.937 | AIN2: 5.521
DI1..4: 1100 | CNT1: 00000 | CNT2: 00002 | AIN1: 1.941 | AIN2: 5.885
DI1..4: 1101 | CNT1: 00000 | CNT2: 00003 | AIN1: 1.937 | AIN2: 6.237
DI1..4: 1111 | CNT1: 00000 | CNT2: 00004 | AIN1: 1.937 | AIN2: 6.581
DI1..4: 1110 | CNT1: 00000 | CNT2: 00005 | AIN1: 1.934 | AIN2: 6.911
DI1..4: 1100 | CNT1: 00000 | CNT2: 00002 | AIN1: 1.937 | AIN2: 7.221
DI1..4: 1101 | CNT1: 00000 | CNT2: 00003 | AIN1: 1.939 | AIN2: 7.512
DI1..4: 1111 | CNT1: 00000 | CNT2: 00004 | AIN1: 1.937 | AIN2: 7.766
DI1..4: 1110 | CNT1: 00000 | CNT2: 00005 | AIN1: 1.937 | AIN2: 7.993
DI1..4: 1100 | CNT1: 00000 | CNT2: 00006 | AIN1: 1.937 | AIN2: 8.183
DI1..4: 1101 | CNT1: 00000 | CNT2: 00007 | AIN1: 1.934 | AIN2: 8.344
DI1..4: 1111 | CNT1: 00000 | CNT2: 00008 | AIN1: 1.934 | AIN2: 8.484

```

This example code runs in 50 ms cyclic loop. Initial values of important service registers (SDC) are defined to be written, and identification registers like hardware and firmware version and CPU ID are read out during startup phase. You can use service registers handling approach provided by this example as a basis for your projects. Completion of SDC startup phase is signalised by message starting with `MONARCO SDC INIT DONE`.

For demonstration, `AOUT1` is driven by constant 2.0 Volts, `AOUT2` is driven by sinusoidal signal between 1.0 Volts and 9.0 Volts. Digital outputs `DOUT3` and `DOUT4` simulate quadrature encoder signal.
For the test, it is expected you connected together AIN1<->AOUT1, AIN2<->AOUT2, DIN3<->DOUT3, DIN4<->DOUT4. COUNTER2 module is switched to quadrature decoder mode.

### Alternative method of acquiring the package via Git

Cloning the repository should be only used if the *npm* registry is not available or it is not desirable to use the *Node.js* package ecosystem.

Install Git:

```
sudo apt install git
```

Clone the repository:

```
git clone https://github.com/monarco/monarco-hat-driver-nodejs.git
```

Change working directory:

```
cd monarco-hat-driver-nodejs
```

Install dependencies in the cloned repository:

```
npm install
```

## License

monarco-hat package and examples provided in this repository are covered by the BSD 3-Clause License. See LICENSE.txt or https://opensource.org/licenses/BSD-3-Clause

Copyright REX Controls s.r.o. http://www.rexcontrols.com, Author: Jiri Faist, <faist@rexcontrols.com>
