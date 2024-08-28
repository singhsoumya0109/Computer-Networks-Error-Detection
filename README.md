# Computer-Networks-Error-Detection

This repository contains a Python implementation of a sender-receiver program that transfers data frames and checks for errors using checksum and Cyclic Redundancy Check (CRC) techniques. The program also includes error injection methods to simulate different types of transmission errors.

## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Usage](#usage)
  - [Sender](#sender)
  - [Receiver](#receiver)
- [Error Injection](#error-injection)
- [Checksum and CRC](#checksum-and-crc)
  - [Checksum](#checksum)
  - [CRC](#crc)

## Introduction

In data communication, ensuring the integrity of transmitted data is crucial. This project demonstrates how to use checksum and CRC to detect errors in data frames during transmission. The sender program can intentionally introduce various types of errors to test the robustness of the error detection methods.

## Features

- **Checksum Calculation:** Implements a binary checksum algorithm for error detection.
- **CRC Calculation:** Supports CRC-8, CRC-10, CRC-16, and CRC-32 for error detection.
- **Error Injection:** Allows the introduction of single-bit, isolated, odd-number, and burst errors.
- **Simulated Data Transmission:** Uses Python's socket library to simulate data transmission between a sender and a receiver over a network.
- **Error Detection:** Compares the received checksum or CRC with the calculated one to detect errors.

## Usage

### Sender

- Prepare a file named `sender_data.txt` containing the binary data you wish to send.
- Run the sender program.
- Choose the type of error (if any) you want to inject during transmission.

### Receiver

- Run the receiver program.
- The receiver will wait for a connection, receive the data, and then check for errors using the selected method (checksum or CRC).

## Error Injection

The program supports the following types of error injection:

- **Single-bit error:** Flips a random single bit in the data.
- **Two isolated single-bit errors:** Flips two random, non-consecutive bits in the data.
- **Odd number of errors:** Flips a random odd number of bits (1, 3, 5, or 7).
- **Burst error:** Flips a consecutive burst of bits (length can be configured).

## Checksum and CRC

### Checksum

The checksum is calculated by dividing the binary data into blocks, performing binary addition on these blocks, and taking the one's complement of the result.

### CRC

The CRC (Cyclic Redundancy Check) is implemented using polynomial division. The program supports multiple CRC standards, including CRC-8, CRC-10, CRC-16, and CRC-32.
