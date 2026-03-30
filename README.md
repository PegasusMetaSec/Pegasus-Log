<div align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=30&duration=3000&pause=1000&color=FF6B6B&center=true&vCenter=true&width=500&lines=PegasusLog;Advanced+Log+System;Real-Time+Monitoring" alt="Typing SVG" />
  
  <img src="https://img.shields.io/badge/Python-3.9+-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/FastAPI-0.95+-009688?style=for-the-badge&logo=fastapi&logoColor=white" alt="FastAPI">
  <img src="https://img.shields.io/badge/React-18.0+-61DAFB?style=for-the-badge&logo=react&logoColor=black" alt="React">
  <img src="https://img.shields.io/badge/PostgreSQL-15-4169E1?style=for-the-badge&logo=postgresql&logoColor=white" alt="PostgreSQL">
</div>

---

## 🐍 Python-Powered Backend

PegasusLog menggunakan **Python** sebagai backbone utama untuk pemrosesan log yang powerful dan efisien:

```python
# core/pegasus_engine.py
from typing import Dict, List, Optional
from datetime import datetime
import asyncio
import json
from dataclasses import dataclass

@dataclass
class LogEntry:
    """Enhanced log entry with metadata"""
    timestamp: datetime
    severity: str
    source: str
    message: str
    metadata: Dict[str, any]
    trace_id: Optional[str] = None

class PegasusLogEngine:
    """Core log processing engine with Python async capabilities"""
    
    def __init__(self):
        self.logs: List[LogEntry] = []
        self.filters = {}
        self._setup_async_handlers()
    
    async def process_log(self, log_data: Dict) -> LogEntry:
        """Process incoming log with Python's async/await"""
        log_entry = LogEntry(
            timestamp=datetime.utcnow(),
            severity=log_data.get('severity', 'INFO'),
            source=log_data.get('source'),
            message=log_data.get('message'),
            metadata=log_data.get('metadata', {}),
            trace_id=log_data.get('trace_id')
        )
        
        # Real-time processing
        await self._analyze_patterns(log_entry)
        await self._apply_filters(log_entry)
        await self._store_log(log_entry)
        
        return log_entry
    
    async def _analyze_patterns(self, log: LogEntry):
        """AI-powered log pattern analysis"""
        patterns = {
            'error_rate': await self._calculate_error_rate(),
            'anomaly_score': await self._detect_anomalies(log),
            'correlation': await self._find_correlations(log)
        }
        
        if patterns['anomaly_score'] > 0.8:
            await self._trigger_alert(log, patterns)
    
    async def stream_logs(self):
        """Async generator for real-time log streaming"""
        while True:
            if self.logs:
                yield self.logs[-1]
            await asyncio.sleep(0.1)
