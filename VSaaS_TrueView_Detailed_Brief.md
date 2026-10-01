# VSaaS Server Room - REVISED for True View Cameras
**Camera Models**: 5MP, 4MP, 2MP (realistic bitrates)  
**Customers**: 25 (100 cameras total)  
**Requirement**: Year-round 24/7 storage (365 days)  
**Location**: India

---

## 📊 REALISTIC STORAGE CALCULATION

### **Camera Specifications & Bitrates**

| Camera | Resolution | FPS | Codec | Bitrate | Per Day | Per Year |
|--------|-----------|-----|-------|---------|---------|----------|
| **5MP** | 2560×1920 | 30 | H.264 | 6 Mbps | 64.8 GB | 23.6 TB |
| **4MP** | 2688×1520 | 30 | H.264 | 4.5 Mbps | 48.6 GB | 17.7 TB |
| **2MP** | 1920×1080 | 30 | H.264 | 3 Mbps | 32.4 GB | 11.8 TB |

**Calculation:**
```
1 Mbps = 128 KB/s
Per day (24 hrs) = 128 KB/s × 86,400 sec = 11.04 GB/Mbps
```

---

### **Your 100 Cameras Distribution**

Assume realistic mix:
- 25 × 5MP cameras = 25 × 64.8 GB/day = 1,620 GB/day
- 25 × 4MP cameras = 25 × 48.6 GB/day = 1,215 GB/day
- 50 × 2MP cameras = 50 × 32.4 GB/day = 1,620 GB/day

**Total Daily**: 1,620 + 1,215 + 1,620 = **4,455 GB/day ≈ 4.5 TB/day**

**Annual Storage (365 days)**: 4.5 × 365 = **1,642 TB ≈ 1.6 PB**

**With RAID-6 redundancy (33% overhead)**: 1,642 × 1.33 = **2,184 TB ≈ 2.2 PB total**

---

## 💾 REVISED SERVER ROOM COSTS

### **Physical Infrastructure** (Same as before)
| Item | Cost |
|------|------|
| Server room AC + Power | ₹15L - ₹30L |
| Racks, cabling, security | ₹8L - ₹15L |
| UPS (20 kVA) | ₹3L - ₹5L |
| Backup Generator (15 kVA) | ₹3L - ₹8L |
| Fire suppression + monitoring | ₹1L - ₹2L |
| **Subtotal** | **₹30L - ₹60L** |

---

### **Server Hardware** (REVISED - smaller than before)

**For 2.2 PB storage requirement:**

| Server Type | Configuration | Cost | Qty | Total |
|------------|---|------|-----|-------|
| **Storage Server (Primary)** | 2× Xeon Gold 6248, 128GB RAM, 120TB NVMe RAID-6 | ₹35L | 1 | ₹35L |
| **Storage Server (Backup)** | 2× Xeon Gold 6248, 128GB RAM, 120TB NVMe RAID-6 | ₹35L | 1 | ₹35L |
| **Web/API Server** | 2× Xeon Silver 4214, 64GB RAM, 2TB SSD | ₹8L | 1 | ₹8L |
| **Database Server** | 2× Xeon Gold 6248, 256GB RAM, 4TB NVMe | ₹20L | 1 | ₹20L |
| **Network** | 10G switches, firewalls, load balancer | ₹8L | 1 | ₹8L |
| **Transcoding Server** (optional) | 2× Xeon Gold with GPU for compression | ₹15L | 1 | ₹15L |

**Subtotal (Servers)**: ₹1,21L

---

### **Storage Infrastructure** (REVISED - more realistic)

| Component | Capacity | Type | Cost |
|-----------|----------|------|------|
| **Primary Storage** | 120 TB | NVMe SSD RAID-6 | ₹60L |
| **Secondary Storage** | 120 TB | HDD SATA RAID-6 | ₹40L |
| **Archive Storage** | 60 TB | HDD Cold Storage | ₹15L |
| **External NAS Backup** | 60 TB | Network backup | ₹20L |
| **SSD Cache Layer** | 10 TB | For hot data | ₹10L |

**Subtotal (Storage)**: ₹1,45L

---

### **REVISED TOTAL ONE-TIME COST**

| Category | Cost |
|----------|------|
| Physical Infrastructure | ₹30L - ₹60L |
| Server Hardware | ₹1,21L |
| Storage | ₹1,45L |
| Network & Misc | ₹20L - ₹30L |
| Software Setup | ₹0 (open-source) |
| **GRAND TOTAL** | **₹2,16L - ₹2,56L (₹2.2 - ₹2.6 Crore)** |

**Breakdown:**
- Storage hardware: 34%
- Servers: 28%
- Physical infra: 16%
- Network: 8%
- Contingency: 14%

---

## 📈 STORAGE GROWTH PROJECTION

| Year | Cameras | Daily | Annual | Cumulative |
|------|---------|-------|--------|-----------|
| **Year 1** | 100 | 4.5 TB | 1.6 PB | 1.6 PB |
| **Year 2** | 150 | 6.8 TB | 2.5 PB | 4.1 PB |
| **Year 3** | 200 | 9.0 TB | 3.3 PB | 7.4 PB |
| **Year 5** | 300 | 13.5 TB | 4.9 PB | ~17 PB |

**Storage strategy**:
- Year 1-2: NVMe + HDD (fast access)
- Year 2+: Tiered storage (hot/warm/cold)
- Year 5: Expand with additional 60TB HDDs

---

## 💸 REVISED MONTHLY OPERATING COSTS

| Expense | Cost | Notes |
|---------|------|-------|
| **Electricity** | ₹25,000-₹45,000 | 2 servers, AC, 24/7 |
| **Cooling/AC** | ₹15,000-₹25,000 | Industrial AC load |
| **Internet** | ₹30,000-₹60,000 | 500-1000 Mbps leased line |
| **Maintenance** | ₹20,000-₹40,000 | HW replacements, patches |
| **Backup Storage** | ₹10,000-₹20,000 | External NAS + cloud |
| **Staff** | ₹30,000-₹60,000 | 1 sysadmin (part-time can start) |
| **Insurance** | ₹10,000-₹15,000 | Equipment + liability |
| **Miscellaneous** | ₹10,000-₹15,000 | Monitoring, licenses |
| **TOTAL/MONTH** | **₹1,50,000-₹2,80,000** |

**Annual Operating**: ₹1.8L - ₹3.4L/month × 12 = **₹21.6L - ₹40.8L**

---

## 💰 FINANCIAL MODEL

### **Revenue Projections**

**Pricing Strategy:**
- **5MP cameras**: ₹4,500/camera/month (premium)
- **4MP cameras**: ₹3,500/camera/month (standard)
- **2MP cameras**: ₹2,500/camera/month (basic)

**Current Portfolio (100 cameras assumed mix):**
```
25 × 5MP @ ₹4,500 = ₹11,25,000/month
25 × 4MP @ ₹3,500 = ₹8,75,000/month
50 × 2MP @ ₹2,500 = ₹12,50,000/month
────────────────────────────────
TOTAL REVENUE = ₹32,50,000/month
```

### **Year 1 Financials**

| Metric | Amount |
|--------|--------|
| **Initial Investment** | ₹2,36,00,000 (₹2.36 Cr) |
| **Monthly Revenue** | ₹32,50,000 |
| **Monthly Ops Cost** | ₹2,00,000 (average) |
| **Monthly Profit** | ₹30,50,000 |
| **Annual Profit** | ₹3,66,00,000 |
| **Break-even Month** | Month 6-7 |
| **Year 1 Net** | +₹1,30,00,000 (positive!) |

### **Year 2+ Financials (scaling to 150 cameras)**

| Metric | Amount |
|--------|--------|
| **Monthly Revenue** | ₹50,00,000 (150 cameras) |
| **Monthly Ops Cost** | ₹2,30,000 (+ storage expansion) |
| **Monthly Profit** | ₹47,70,000 |
| **Annual Profit** | ₹5,72,40,000 |
| **5-Year Cumulative Profit** | ₹15+ Crores |

---

## 🎯 STORAGE STRATEGY BY TIER

### **Tier 1: Premium (5MP) Customers**
- **Retention**: 365 days online
- **Speed**: NVMe RAID-6 (fastest)
- **Access**: Real-time, instant playback
- **Cost/TB/month**: ₹0.5L

### **Tier 2: Standard (4MP) Customers**
- **Retention**: 180 days online + 180 days archive
- **Speed**: HDD RAID-6 (fast)
- **Access**: 1-2 second startup
- **Cost/TB/month**: ₹0.35L

### **Tier 3: Basic (2MP) Customers**
- **Retention**: 90 days online + 270 days archive
- **Speed**: Archive storage (slow)
- **Access**: 5-10 second startup
- **Cost/TB/month**: ₹0.2L

**Auto-tiering**: Videos automatically move from NVMe → HDD → Archive based on age

---

## 🔧 REVISED VSAAS ARCHITECTURE FOR TRUE VIEW

```
True View Cameras (5MP/4MP/2MP)
    ↓ (RTSP stream)
Camera Ingestion Server
    ├─ RTMP Ingest (1935)
    ├─ Video validation
    ├─ Bitrate analysis (adaptive)
    └─ Queue to MinIO
    ↓
MinIO Object Storage
    ├─ 120TB Primary NVMe
    ├─ 120TB Secondary HDD
    ├─ Auto-tiering by age
    └─ RAID-6 redundancy (can lose 2 drives)
    ↓
HLS Streaming Pipeline
    ├─ FFmpeg segmentation (10s chunks)
    ├─ Playlist generation (.m3u8)
    ├─ Multi-bitrate (optional H.265 compression)
    └─ Redis cache for playlists
    ↓
Web Dashboard
    ├─ Live view (HLS player)
    ├─ Playback (date/time scrubber)
    ├─ Export MP4
    ├─ Analytics dashboard
    └─ Mobile app (React Native)
    ↓
Customers
    └─ View via browser/mobile anytime
```

---

## 📋 HARDWARE ORDERING CHECKLIST

### **Servers to Order**

```
1. Storage Server 1
   - 2× Intel Xeon Gold 6248 (24-core)
   - 128GB DDR4 RAM
   - 120TB NVMe SSD (RAID-6 controller card)
   - Dual redundant PSU
   - Est: ₹35,00,000

2. Storage Server 2 (Backup/Failover)
   - Same as above
   - Est: ₹35,00,000

3. Web/API Server
   - 2× Intel Xeon Silver 4214 (12-core)
   - 64GB DDR4 RAM
   - 2TB NVMe SSD
   - Est: ₹8,00,000

4. Database Server
   - 2× Intel Xeon Gold 6248
   - 256GB DDR4 RAM (for large result sets)
   - 4TB NVMe SSD
   - Est: ₹20,00,000

5. Network Equipment
   - 10G managed switch
   - L4 load balancer (FortiGate or Palo Alto)
   - Firewall (hardware)
   - Est: ₹8,00,000

6. Optional: GPU Server (for transcoding)
   - 2× Xeon Gold
   - 2× NVIDIA A100 GPUs
   - 256GB RAM
   - Est: ₹15,00,000
```

### **Storage Components**

```
1. NVMe Drives (120TB)
   - 12× Samsung 990 Pro 10TB
   - Est: ₹60,00,000

2. HDD Drives (120TB archive)
   - 30× WD Gold 4TB
   - Est: ₹40,00,000

3. External NAS Backup
   - Synology or QNAP 60TB
   - Est: ₹20,00,000

4. UPS Battery System
   - 20kVA online UPS
   - Est: ₹3,50,000

5. Power Distribution
   - PDU, surge protection
   - Est: ₹50,000
```

---

## 🚀 SETUP TIMELINE (REVISED)

| Week | Task | Details |
|------|------|---------|
| **W1** | Order hardware | Submit POs for servers, storage, network |
| **W2-3** | Physical setup | Server room AC, power, racks, cabling |
| **W4-5** | Install OS | Ubuntu Server, BIOS config, drivers |
| **W6** | Deploy storage | MinIO cluster, NVMe/HDD formatting, RAID |
| **W7** | Database setup | PostgreSQL, Redis, replication |
| **W8-10** | SaaS development | API, frontend, ingestion service (hire devs) |
| **W11** | Testing | Load testing, failover drills, security |
| **W12** | Beta launch | 5-10 customers on new system |
| **W14** | Full rollout | All 25 customers migrated |
| **W16** | Optimization | Tuning, monitoring, scaling |

---

## 🔒 CRITICAL INFRASTRUCTURE SPECS

### **Redundancy Architecture**

```
Primary Storage Server
    ├─ RAID-6 NVMe (120TB)
    ├─ Dual 10G uplinks
    ├─ Active
    └─ MinIO cluster node 1

Backup Storage Server
    ├─ RAID-6 NVMe (120TB)
    ├─ Dual 10G uplinks
    ├─ Hot standby
    └─ MinIO cluster node 2

External NAS
    ├─ Daily backup (incremental)
    ├─ Off-site location (office/home)
    └─ MinIO cluster node 3 (optional)

Load Balancer
    ├─ Routes traffic to active storage
    ├─ Automatic failover if node down
    └─ Health checks every 10s
```

**Availability**: 99.95% uptime (4.38 hours downtime/year)

---

## 📊 CAPACITY PLANNING (5-YEAR ROADMAP)

### **Year 1: Bootstrap**
- 100 cameras (5MP/4MP/2MP mix)
- 1.6 PB/year generated
- 2.2 PB storage (with RAID)
- 2 storage servers + 1 backup
- **Revenue**: ₹32.5L/month

### **Year 2: Growth**
- 150 cameras (add 50 new)
- 2.5 PB/year generated
- 3.3 PB storage needed
- Add 60TB external drive
- **Revenue**: ₹50L/month

### **Year 3: Expansion**
- 200 cameras
- 3.3 PB/year
- 4.4 PB storage
- Add 3rd storage server
- **Revenue**: ₹65L/month

### **Year 5: Enterprise**
- 300+ cameras
- 5+ PB/year
- 6+ PB storage
- Distributed across 3+ sites
- **Revenue**: ₹100L+/month

---

## ⚡ PERFORMANCE SPECS

### **Streaming Performance**
```
5MP cameras @ 6 Mbps:
- 10 concurrent streams = 60 Mbps = 7.5 MB/s
- Bandwidth required = 600 Mbps (1Gbps leased line)

All 100 cameras streaming simultaneously:
- Total = 450 Mbps (well within 1Gbps)
- Peak bursts = 600 Mbps (add 200 Mbps buffer)
- Recommended = 1.5-2 Gbps leased line
```

### **Storage I/O**
```
Write: 4.5 TB/day ÷ 86,400 sec = 52 MB/s
Read: Peak 100 customers × 6 Mbps = 75 MB/s
Both: 127 MB/s (NVMe RAID can handle 500+ MB/s)
```

### **Database Load**
```
Video segments: ~4,500/day (100 cameras)
Queries: ~50/second during peak
PostgreSQL can handle 1000+ TPS easily
Redis cache reduces DB load 80%
```

---

## 📱 VSAAS FEATURES FOR TRUE VIEW CAMERAS

### **MVP Features (Week 8-10)**
1. ✅ Live streaming (HLS, adaptive bitrate)
2. ✅ Playback by date/time
3. ✅ Multi-camera dashboard
4. ✅ User management (admin/viewer roles)
5. ✅ Cloud export (MP4 download)

### **Phase 2 (Week 14-16)**
6. Motion detection alerts
7. Snapshot capture
8. Video search (by motion/time)
9. Mobile app (iOS/Android)
10. Analytics (storage used, bandwidth)

### **Phase 3 (Month 4-6)**
11. AI object detection (person, vehicle, animal)
12. Heat maps & analytics
13. Custom reports
14. Two-factor authentication
15. API for 3rd-party integration

---

## 🎬 DATABASE SCHEMA FOR TRUE VIEW

```sql
-- Customers Table
CREATE TABLE customers (
  id SERIAL PRIMARY KEY,
  name VARCHAR(255),
  email VARCHAR(255) UNIQUE,
  subscription_tier ENUM('basic', 'standard', 'premium'),
  storage_limit_tb INT,
  created_at TIMESTAMP
);

-- Cameras Table
CREATE TABLE cameras (
  id SERIAL PRIMARY KEY,
  customer_id INT REFERENCES customers(id),
  name VARCHAR(255),
  model VARCHAR(50),  -- "5MP", "4MP", "2MP"
  rtsp_url VARCHAR(255),
  bitrate_mbps INT,  -- 6, 4.5, or 3
  resolution VARCHAR(20),  -- 2560x1920, 2688x1520, 1920x1080
  status ENUM('active', 'inactive', 'error'),
  created_at TIMESTAMP,
  INDEX (customer_id, created_at)
);

-- Video Segments (partitioned by date for performance)
CREATE TABLE video_segments_2026_09 (
  id BIGSERIAL PRIMARY KEY,
  camera_id INT,
  timestamp TIMESTAMP,
  duration_seconds INT,
  size_bytes BIGINT,
  bitrate_mbps INT,
  minio_path VARCHAR(255),
  is_archived BOOLEAN DEFAULT false,
  storage_tier ENUM('nvme', 'hdd', 'cold'),
  created_at TIMESTAMP,
  INDEX (camera_id, timestamp)
) PARTITION BY RANGE (timestamp);

-- Add monthly partitions
CREATE TABLE video_segments_2026_10 PARTITION OF video_segments;

-- Alerts Table
CREATE TABLE alerts (
  id SERIAL PRIMARY KEY,
  camera_id INT REFERENCES cameras(id),
  alert_type VARCHAR(50),  -- motion, object_detection
  timestamp TIMESTAMP,
  image_path VARCHAR(255),
  metadata JSON,  -- {"detected_objects": ["person", "car"]}
  INDEX (camera_id, timestamp)
);

-- Storage Usage Tracking
CREATE TABLE storage_metrics (
  id SERIAL PRIMARY KEY,
  camera_id INT REFERENCES cameras(id),
  timestamp TIMESTAMP,
  daily_used_gb FLOAT,
  tier_distribution JSON,  -- {nvme: 50, hdd: 40, cold: 10}
  INDEX (camera_id, timestamp)
);
```

---

## 🛡️ SECURITY CONFIGURATION

### **Firewall Rules**
```
INBOUND:
- Port 443 (HTTPS) - Dashboard access
- Port 1935 (RTMP) - Camera ingest (restricted to local IPs)
- Port 22 (SSH) - Admin only (bastion host)

OUTBOUND:
- Allow NTP (time sync)
- Allow DNS
- Block all else (except backup to NAS)

DENY:
- All HTTP (redirect to HTTPS)
- All non-whitelisted IPs
```

### **SSL/TLS Certificates**
```
- Self-signed for camera RTMP (internal)
- Let's Encrypt for dashboard HTTPS (auto-renew)
- Client certificates for admin SSH access
```

### **Data Encryption**
```
- At-rest: Transparent storage encryption (dm-crypt)
- In-transit: TLS 1.3 for all network
- Backups: AES-256 encrypted
- Database: Encrypted columns for sensitive data
```

---

## 📞 NEXT STEPS

1. **Week 1**: Get board approval, allocate ₹2.5 Cr budget
2. **Week 2**: Submit hardware orders (lead time: 2-3 weeks)
3. **Week 3**: Start server room construction
4. **Week 4**: Begin hiring (1 sysadmin, 2-3 devs)
5. **Week 5-6**: Install hardware, OS, software stack
6. **Week 8**: Start SaaS development
7. **Week 12**: Beta launch to first 5 customers
8. **Week 16**: Full production launch

**Budget Allocation:**
- Hardware: ₹2,36,00,000
- Development: ₹15,00,000 (outsource or hire)
- Contingency: ₹30,00,000
- **Total**: ₹2,81,00,000 (₹2.81 Cr)

**ROI**: Break-even Month 6-7, then ₹30-50L profit/month!

---

**Ready to order? Let me help you create the technical RFP (Request for Proposal) for hardware vendors!**
