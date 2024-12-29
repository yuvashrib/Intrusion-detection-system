
# Dataset Overview  

The project utilizes the **KDD Cup 1999 dataset**, a widely used benchmark for evaluating intrusion detection systems (IDS). This dataset simulates a military network environment, containing labeled records of network connections categorized as either **"normal"** or various types of attacks, including:  

- **Denial of Service (DoS):** Overwhelms system resources.  
- **Probing:** Scans to gather information about the target system.  
- **Remote-to-Local (R2L):** Attempts unauthorized access to local resources.  
- **User-to-Root (U2R):** Seeks administrative privileges after gaining initial access.  

---

## Dataset Features  

The dataset consists of **41 features** describing each network connection, categorized as follows:  

### 1. Connection Details  
- `duration`: Connection length in seconds.  
- `protocol_type`: Protocol used (e.g., TCP, UDP, ICMP).  
- `service`: Network service accessed (e.g., HTTP, FTP).  
- `flag`: Status of the connection (e.g., `SF` for "normal").  

### 2. Traffic Metrics  
- `src_bytes`: Data bytes sent from the source.  
- `dst_bytes`: Data bytes sent to the destination.  
- `count` & `srv_count`: Number of connections to the same host and service.  

### 3. Error Rates  
- `serror_rate`: Rate of connections with SYN errors.  
- `rerror_rate`: Rate of connections with ACK errors.  

### 4. Session Indicators  
- `logged_in`: Whether the user is logged in (1 or 0).  
- `num_failed_logins`: Number of failed login attempts.  
- `is_guest_login`: Indicates guest login attempts.  

### 5. Host Behavior  
- `dst_host_count`: Number of connections to the destination host.  
- `dst_host_same_srv_rate`: Rate of connections to the same service on the destination host.  

### 6. Anomalous Activity Indicators  
- `land`: Binary flag for same source and destination IP.  
- `lnum_compromised`: Number of compromised systems.  
- `lroot_shell`: Binary flag indicating root shell access.  

---

## Label Column  

The dataset includes a **label column** that classifies each connection as either:  
- **Normal**  
- **Attack Types:** (e.g., DoS, Probe, R2L, U2R).  

---

## Applications  

This dataset is ideal for building machine learning models to detect malicious network activities by leveraging its extensive features. The balanced representation of normal and attack traffic provides a solid foundation for:  

1. **Training classifiers** to identify intrusions.  
2. **Evaluating model performance** using key metrics.  

For more details, refer to the [KDD Cup 1999 Dataset Documentation](http://kdd.ics.uci.edu/databases/kddcup99/kddcup99.html).  
