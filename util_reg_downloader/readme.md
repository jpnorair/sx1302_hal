	J P N O R A I R
	  (C)2020 JP Norair

# Utility to download all registers

## 1. Introduction

This utility downloads all the registers in the SX1302 and exports them as CSV or JSON to stdout.

## 2. Command line options

### 2.1. General options ###

`-h`
will display a short help and version informations.

### 2.2. SPI options ###

`-d filename`
use the Linux SPI device driver, but with an explicit path, for systems with several SPI device drivers, or uncommon numbering scheme.

### 2.3. Output Format ###

`-f format`
Specify CSV (format=CSV), or JSON (format=JSON) as the output format.  Default is CSV.

