# QPSK-Receiver-Full-Demodulation-Pipeline
<p align="justify">
This project demonstrates a complete Quadrature Phase Shift Keying (QPSK) receiver, showcasing the entire demodulation process from a modulated signal to recovered digital data. The system encompasses all crucial stages of QPSK demodulation, including signal acquisition, carrier recovery, symbol synchronization, and bit extraction. It is designed to provide a clear and practical understanding of digital communication principles, making it suitable for students, researchers, and embedded systems developers. With a strong focus on simplicity and clarity, this project effectively bridges theoretical concepts in digital communications with real-world implementation.
</p>

## Part 1: Validation of Serial to Parallel Functionality
<p align="justify">
To generate a QPSK (Quadrature Phase Shift Keying) signal, the Sequence Generator module begins by modeling the digital data. Next, the 2-bit Serial-to-Parallel Converter module divides the data into even and odd bit streams. This important step reduces the symbol rate by half and sets the data up for independent modulation of the I (in-phase) and Q (quadrature) channels.
</p>

<p align = "center">
<img width="1024" height="804" alt="image" src="https://github.com/user-attachments/assets/d98cb6d3-b617-4c68-ad43-20d91e499087" />
</p>

<p align = "center">
<em> Figure 1.0: Connecting Diagram </em>
</p>
    
<p align = "center">
<img width="1024" height="804" alt="image" src="https://github.com/user-attachments/assets/9c84cc37-52ab-4272-b29d-3b97164308e5" />
</p>

<p align = "center">
<em> Figure 1.1: Connecting Diagram </em>
</p>

<p align="justify">
The outputs from the Serial-to-Parallel Converter module are directed to the inputs of the 2-bit Parallel-to-Serial Converter module. This process is the final step in recovering the original message from a QPSK signal. Although the digital signal at the output of the Sequence Generator module is repetitive, its pulse sequence is too irregular for the oscilloscope to display a stable reading using that signal alone. To resolve this, the oscilloscope’s External Trigger Source is connected to the SYNC output of the Sequence Generator. The SYNC output generates a single marker pulse that aligns with the first bit of the data output from the Sequence Generator module.
</p>

<details>
  <summary> PART 1: OUTPUT RESULTS </summary>

<p align = "center">
<img width="1024" height="804" alt="image" src="https://github.com/user-attachments/assets/421879d2-0d80-4b27-8246-8e7700841b5a" />
</p>

<p align = "center">
<img width="1024" height="804" alt="image" src="https://github.com/user-attachments/assets/06e542b4-b568-46b2-a74c-756dce5df0a1" />
</p>

<p align = "center">
<img width="1024" height="804" alt="image" src="https://github.com/user-attachments/assets/6063129f-ea65-4a42-8426-f81dddf221b4" />
</p>

<p align = "center">
<img width="1024" height="804" alt="image" src="https://github.com/user-attachments/assets/27c24e21-ca2b-4adb-bdcf-601b2be53a96" />
</p>

<p align = "center">
<img width="1024" height="804" alt="image" src="https://github.com/user-attachments/assets/0486c46e-fbca-4cd3-9df1-fd994b792f06" />
</p>

<p align = "center">
<img width="1024" height="804" alt="image" src="https://github.com/user-attachments/assets/681e2a81-1d24-4162-b2b3-2006e78ab4bf" />
</p>

  </p>
</details>

## Part 2: Producing the QPSK Waveform
<p align="justify">
Generating the QPSK waveform involves converting a serial digital bit stream into two parallel streams for even and odd bits, modulating quadrature carriers with each of these streams, and summing the results to produce a signal that transmits two bits per symbol.
</p>

<p align = "center">
<img width="1024" height="804" alt="image" src="https://github.com/user-attachments/assets/c151f785-6f8a-42a1-81e6-041fef0c800d" />
</p>

<p align = "center">
<em> Figure 2.0: Connecting Diagram </em>
</p>

<p align = "center">
<img width="1024" height="804" alt="image" src="https://github.com/user-attachments/assets/4f00a963-de38-4b3e-81a7-3c8c511ec6de" />
</p>

<p align = "center">
<em> Figure 2.1: Connecting Diagram </em>
</p>

<p align="justify">
Excluding the digital data modeling, this setup can be represented by the block diagram shown at the top. The two outputs from the bit-splitter are each connected to independent multiplier modules. Each multiplier module also receives an input from a 100 kHz sine wave, with the two sine waves being exactly 90° out of phase, this phase difference is a fundamental requirement for Quadrature Phase Shift Keying (QPSK).
</p>

<p align="justify">
To obtain a stable trace on the oscilloscope display, the Trigger Source signal is taken from the SYNC output of the Sequence Generator module. However, this signal is passed through a divide-by-2 circuit. This divider is necessary because the digital signals used to phase modulate the two carriers operate at a frequency that is equal to half the bit rate of the original digital data signal.
</p>

<details>
  <summary> PART 2: OUTPUT RESULTS </summary>

<p align = "center">
<img width="1024" height="804" alt="image" src="https://github.com/user-attachments/assets/2caf017a-3f82-43c9-85b2-6bec6d6165d9" />
</p>

<p align = "center">
<img width="1024" height="804" alt="image" src="https://github.com/user-attachments/assets/04ee7ba7-1fbd-4731-8e63-a115d1fa4dfc" />
</p>

<p align = "center">
<img width="1024" height="804" alt="image" src="https://github.com/user-attachments/assets/ab69d289-0df0-4d97-b17c-1dcbebe806f8" />
</p>

<p align = "center">
<img width="1024" height="804" alt="image" src="https://github.com/user-attachments/assets/dd0c0949-3acf-4029-8b54-56a8f1e2d2a6" />
</p>

<p align = "center">
<img width="1024" height="804" alt="image" src="https://github.com/user-attachments/assets/d5172d1b-9795-42ff-ae29-3b05e6f5276d" />
</p>

<p align = "center">
<img width="1024" height="804" alt="image" src="https://github.com/user-attachments/assets/971b476f-1d3e-41a7-a515-dfff9384ddee" />
</p>

<p align = "center">
<img width="1024" height="804" alt="image" src="https://github.com/user-attachments/assets/8e683703-483a-436c-b9ba-263dd2819cf7" />
</p>

<p align = "center">
<img width="1024" height="804" alt="image" src="https://github.com/user-attachments/assets/cf7f6040-f089-46d7-970d-b815e3412e67" />
</p>

<p align = "center">
<img width="1024" height="804" alt="image" src="https://github.com/user-attachments/assets/30161ac2-2450-48a0-9466-9f2d46c468fe" />
</p>

<p align = "center">
<img width="1024" height="804" alt="image" src="https://github.com/user-attachments/assets/c440709d-5db1-4b26-92e1-cf0ce35ac08b" />
</p>

<p align = "center">
<img width="1024" height="804" alt="image" src="https://github.com/user-attachments/assets/59e36ae0-112b-451a-b1e4-47f87750b6c0" />
</p>

<p align = "center">
<img width="1024" height="804" alt="image" src="https://github.com/user-attachments/assets/8ff659fe-fc28-42cc-a347-b8faef998d2b" />
</p>

<p align = "center">
<img width="1024" height="804" alt="image" src="https://github.com/user-attachments/assets/797d871a-3305-4edb-89c6-95d29695626d" />
</p>

  </p>
</details>

## Part 3: 









