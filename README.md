#CSUN ECE 16942
##Getting started with Git
**Name: Daniel Puga  
Date: 8-26-24**

1. FPGA
2. VHDL
3. Verilog

![CSUN_ENG](./img/csun_eng_logo.png)

[Github Profile](https://github.com/Dannnny2525)
``` vhdl 
library ieee;
use ieee.std_logic_1164.all;
use ieee.std_logic_unsigned.all;

entity counter is
    port (
        clk : in std_logic;
        reset : in std_logic;
        enable : in std_logic;
        count : out std_logic_vector(3 downto 0)
    );
end counter;

architecture Behavioral of counter is
    signal pre_count : std_logic_vector(3 downto 0);
begin
    process (clk, enable, reset)
    begin
        if reset = '1' then
            pre_count <= "0000";
        elsif (clk = '1' and clk'event) then
            if enable = '1' then
                pre_count <= pre_count + "1";
            end if;
        end if;
    end process;
    count <= pre_count;
end Behavioral;

![git status before stage](./img/git_stat.png)



