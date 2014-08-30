urjtag - support for Analog Discovery FPGA

Build
=====

Simply run the following commands:

    $ ./autogen.sh --disable-bsdl
    $ make -j4

If you want to install urjtag in `/usr/local`:

    $ sudo make install

Usage
=====

Launch urjtag:

    $ sudo ./src/apps/jtag/jtag

Or if you installed it in `/usr/local`:

    $ sudo /usr/local/bin/jtag

In the urjtag command prompt:

    jtag> cable analogdiscovery driver=ftdi-mpsse
    Connected to libftdi driver.

Then, try to detect the JTAG chain:

    jtag> detect
    IR length: 6
    Chain length: 1
    Device Id: 01000100000000000010000010010011 (0x44002093)
        Manufacturer: Xilinx (0x093)
        Part(0):      xc6slx16 (0x4002)
        Stepping:     4
        Filename:     /usr/local/share/urjtag/xilinx/xc6slx16/xc6slx16_cpg196

If you want to load a bitstream to the FPGA:

    jtag> pld load ../path/to/files.bit

Verify the successfullness of the load operation:

    jtag> pld status

...to be continued.

Varia
=====

 * Official urjtag repository can be found here http://urjtag.org/

License
=======

This patch is released under the same license as urjtag, the GNU General Public License.

