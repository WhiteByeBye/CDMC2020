# **Task 2: IoTMal2020-CDMC: IOT Malware Detection**

Based on the byte sequences collected at the entry points of ELF files as discriminant features and the malware families of the programs as training labels, the participants are required to perform a classification task to predict the malware families of the test samples. The dataset consists of 72,638 samples generated following the procedure below: First, a collection of malicious and benign Linux programs in ELF format were collected from various sources. Then, from each of these programs, the first 2K bytes (0-padded if the file is not long enough) starting at the entry point of the file were extracted. These ASCII strings were then encoded by a simple encryption cipher to remove the sensitive information and fed to a base64 encoder to yield readable radix-64 representations. Label (family type of malware) of the binary files are determined by the state-of-art anti-virus engines.

## **File Format**

The two .csv files share the same format as described below.

Except the first header line, each of the lines provide 3 characterizing features for a unique ELF file.

- "Family" column indicates the family type of the binary file, and is taken as class label of this classification task.
- "CP" column indicates the CPU architecture on which the file is compiled. Participant can determine whether or not to use it as side information to improve the prediction performance.
- "ByteSequence" column is the encoded first 2K bytes of the ELF files following the aforementioned steps.

The difference of the test file from the training file is that the "Family" column of the lines are all assigned to "Unknown".

## **Task**

The participants are required to provide the prediction of labels of the test samples based on information provided in the task.

## **Credits and Clarifications**

The original analysis data of IoT malware classification task was kindly contributed by Taiwan Information Security Center (TWISC). The data was processed by the CDMC 2020 committee with all sensitive information removed.