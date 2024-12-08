# Python_Day14

#Mini-Project: Design a Signal Data Analyzer Using OOP Concepts
#Step 1: Define the SignalData Class
class SignalData:
    def __init__(self, value, timestamp):
        self.value = value
        self.timestamp = timestamp

# Example usage:
signal = SignalData(23.5, "2024-12-14 10:00:00")
print(f"Value: {signal.value}, Timestamp: {signal.timestamp}")


#Step 2: Define the SignalAnalyzer Class
class SignalAnalyzer:
    def __init__(self):
        self.signals = []
    
    def add_signal(self, signal):
        self.signals.append(signal)
    
    def average_value(self):
        if not self.signals:
            return 0
        total = sum(signal.value for signal in self.signals)
        return total / len(self.signals)
    
    def max_value(self):
        if not self.signals:
            return None
        return max(signal.value for signal in self.signals)
    
    def min_value(self):
        if not self.signals:
            return None
        return min(signal.value for signal in self.signals)

# Example usage:
analyzer = SignalAnalyzer()
analyzer.add_signal(SignalData(23.5, "2024-12-14 10:00:00"))
analyzer.add_signal(SignalData(24.1, "2024-12-14 10:01:00"))
analyzer.add_signal(SignalData(22.8, "2024-12-14 10:02:00"))
print(f"Average Value: {analyzer.average_value()}")
print(f"Max Value: {analyzer.max_value()}")
print(f"Min Value: {analyzer.min_value()}")
