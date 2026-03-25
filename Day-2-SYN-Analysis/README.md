SYN TRAFFIC ANALYSIS & CONNECTION BEHAVIOR INVESTIGATION (DAY2)

1. ENVIRONMENT
Tool: Wireshark
Network: Wi-Fi
System: Local machine traffic analysis

2. ACTIVITY

Network traffic was captured using Wireshark during normal system operation. The analysis focused on identifying TCP SYN packets and evaluating connection behavior to detect potential anomalies or malicious patterns.

3. PACKET ANALYSIS
Source: 192.168.x.x (local system)
Destination: External IP addresses (20.42.x.x, 113.44.x.x)
Ports: 443 (HTTPS), 80 (HTTP)
Observed Pattern:
Multiple TCP SYN packets sent from the local system
Presence of repeated TCP retransmissions
SYN packets targeting the same destinations and ports
Time Behavior:
0.000 → 1.1 → 2.6 → 6.8 seconds
Gradual increase in time intervals between retransmissions

4. OBSERVATIONS
The traffic originates from a single internal host attempting to establish connections with external web servers
Repeated SYN retransmissions indicate unsuccessful or delayed connection establishment
The increasing time intervals between retransmissions follow normal TCP retry logic
No evidence of:
Rapid SYN flooding
Multiple port targeting (port scanning)
Repeated authentication attempts (brute force)

5. CONCLUSION
The observed traffic represents normal connection retry behavior due to network latency, packet loss, or temporary unavailability of the destination servers. The presence of TCP retransmissions is consistent with standard TCP mechanisms for ensuring reliable communication.

No indicators of malicious activity such as brute force attacks, port scanning, or denial-of-service behavior were identified.

6. ANALYST PERSPECTIVE

From a SOC standpoint, this traffic was evaluated for abnormal patterns and potential threats. The analysis confirms that the behavior aligns with legitimate network communication rather than adversarial activity. Understanding the distinction between retransmissions and attack patterns is critical in avoiding false positives during incident analysis.

7. KEY LEARNING OUTPUTS
Identification and filtering of SYN packets
Understanding TCP retransmission behavior
Differentiating normal network issues from attack patterns
Interpreting time-based packet behavior
