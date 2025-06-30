# ISO 27001:2022 Information Security Management System (ISMS) Golden Configurations

This repository contains ISO 27001:2022 compliant golden configuration templates for network infrastructure implementing Information Security Management System (ISMS) controls. These configurations align with the updated Annex A controls and support comprehensive information security management.

## Overview

ISO 27001:2022 represents the latest iteration of the international standard for information security management systems. The 2022 revision includes:

- **93 security controls** organized into 4 themes (down from 114 controls in 14 domains)
- **11 new controls** addressing modern security challenges
- **Simplified structure** with organizational, people, physical, and technological controls
- **Enhanced focus** on cloud security, supply chain risk, and operational resilience

## Annex A Control Categories

### Organizational Controls (A.5)
Information security policies, risk management, supplier relationships, and incident management.

### People Controls (A.6) 
Security awareness, terms of employment, disciplinary processes, and remote working.

### Physical Controls (A.7)
Physical security perimeters, equipment protection, and secure disposal.

### Technological Controls (A.8)
User access management, cryptography, system security, and network security controls.

## Key Network Security Controls Implemented

### Control 8.20 - Network Security
Comprehensive network security management including:
- Network isolation and sub-network segmentation
- Traffic filtering and protocol management
- Visible device inventory and monitoring
- Firmware and configuration management

### Control 8.9 - Configuration Management
Secure configuration lifecycle management:
- Configuration baselines and standards
- Change control and approval processes
- Configuration monitoring and drift detection
- Automated remediation capabilities

### Control 8.15 - Logging
Comprehensive audit logging and monitoring:
- Security event logging and correlation
- Log integrity protection and retention
- Real-time monitoring and alerting
- Incident investigation capabilities

## Repository Structure

```
├── configs/
│   ├── organizational-controls/     # A.5 - Policy and governance
│   ├── people-controls/            # A.6 - Human resource security
│   ├── physical-controls/          # A.7 - Physical and environmental
│   └── technological-controls/     # A.8 - Technical security controls
├── variables/
│   ├── production.yml             # Production ISMS variables
│   ├── staging.yml                # Staging environment
│   └── development.yml            # Development environment
├── docs/
│   ├── annex-a-mapping.md         # Control implementation mapping
│   ├── risk-assessment.md         # Risk assessment procedures
│   └── isms-procedures.md         # ISMS operational procedures
└── audit/
    ├── evidence/                  # Audit evidence templates
    └── reports/                   # Compliance reporting
```

## Information Classification Scheme

### VLAN Architecture for Information Classification
- **VLAN 300**: Management Network
- **VLAN 400**: Business Critical Information
- **VLAN 450**: Internal Use - Classified
- **VLAN 460**: Public Information
- **VLAN 470**: Restricted Access

### Data Classification Controls
Each VLAN implements appropriate security controls based on information classification:
- **Restricted**: Highest security with encryption, strict access controls
- **Confidential**: Strong access controls and monitoring
- **Internal**: Standard organizational controls
- **Public**: Basic integrity and availability controls

## Core Security Features

### Network Security (Control 8.20)
- **Sub-network Isolation**: Logical separation of security domains
- **Traffic Filtering**: Protocol-specific filtering and inspection
- **Network Monitoring**: Continuous visibility and anomaly detection
- **Configuration Management**: Automated configuration compliance

### Access Management (Control 5.15)
- **Identity Management**: Centralized user identity lifecycle
- **Access Control**: Role-based access with least privilege
- **Privileged Access**: Enhanced controls for administrative access
- **Access Review**: Regular access certification processes

### Information Protection (Control 8.24)
- **Data Classification**: Automated data labeling and handling
- **Encryption**: Data protection in transit and at rest
- **Data Loss Prevention**: Monitoring and control of data flows
- **Backup Security**: Protected backup and recovery procedures

## Quick Start

### Prerequisites
- ISO 27001:2022 gap analysis completed
- Information asset register established
- Risk assessment and treatment plan approved
- ISMS policy framework documented

### Deployment Process

1. **Clone Repository:**
   ```bash
   git clone https://github.com/keepithuman/iso-27001-2022-golden-configs.git
   cd iso-27001-2022-golden-configs
   ```

2. **Configure ISMS Variables:**
   ```bash
   cp variables/production.yml.example variables/production.yml
   # Update with your ISMS-specific values
   ```

3. **Deploy Controls:**
   ```bash
   # Deploy organizational controls
   # Deploy technological controls
   # Validate implementation
   ```

## ISO 27001:2022 Control Implementation

### Organizational Controls (A.5)
| Control | Description | Configuration File |
|---------|-------------|-------------------|
| A.5.1 | Information security policy | `organizational-controls/security-policy.cfg` |
| A.5.15 | Access control | `organizational-controls/access-management.cfg` |
| A.5.23 | Information security in project management | `organizational-controls/project-security.cfg` |

### Technological Controls (A.8)
| Control | Description | Configuration File |
|---------|-------------|-------------------|
| A.8.9 | Configuration management | `technological-controls/config-management.cfg` |
| A.8.15 | Logging | `technological-controls/audit-logging.cfg` |
| A.8.20 | Networks security | `technological-controls/network-security.cfg` |
| A.8.24 | Use of cryptography | `technological-controls/cryptography.cfg` |

## Environment Variables

### Core ISMS Variables
```yaml
# Organization Information
organization_name: "SecureCorp"
domain_name: "securecorp.com"
isms_scope: "Global IT Infrastructure"

# Information Classification
classification_levels:
  - "PUBLIC"
  - "INTERNAL"
  - "CONFIDENTIAL" 
  - "RESTRICTED"

# Network Architecture
management_vlan: "300"
business_critical_vlan: "400"
internal_classified_vlan: "450"
public_info_vlan: "460"
restricted_access_vlan: "470"

# Security Infrastructure
siem_server: "10.3.100.15"
certificate_authority: "10.3.100.20"
key_management_server: "10.3.100.25"

# Monitoring and Logging
log_retention_period: "2555"  # 7 years
audit_log_server: "10.3.100.30"
security_monitoring: "24x7"

# Risk Management
risk_appetite: "LOW"
security_objectives:
  - "CONFIDENTIALITY"
  - "INTEGRITY" 
  - "AVAILABILITY"
```

## Risk Assessment Integration

### Asset Classification
All network assets are classified according to:
- **Criticality**: Business impact assessment
- **Sensitivity**: Information classification level
- **Vulnerability**: Security weakness assessment
- **Threat Level**: Current threat landscape

### Control Effectiveness
Regular assessment of control effectiveness through:
- **Technical Testing**: Automated security scanning
- **Process Review**: Operational procedure validation
- **Management Review**: Strategic alignment assessment
- **External Audit**: Independent verification

## ISMS Operational Procedures

### Monitoring and Review
- **Daily**: Security event monitoring and response
- **Weekly**: Access review and anomaly investigation
- **Monthly**: Control effectiveness assessment
- **Quarterly**: Risk assessment review and update
- **Annually**: Management review and ISMS improvement

### Incident Management
- **Detection**: Automated monitoring and manual reporting
- **Classification**: Severity and impact assessment
- **Response**: Coordinated incident response team
- **Recovery**: Business continuity and service restoration
- **Lessons Learned**: Continuous improvement process

### Change Management
- **Impact Assessment**: Security impact evaluation
- **Approval Process**: Risk-based approval workflow
- **Implementation**: Controlled deployment procedures
- **Verification**: Post-implementation validation
- **Documentation**: Complete change records

## Compliance and Certification

### Internal Audit Program
- **Planning**: Risk-based audit scheduling
- **Execution**: Systematic control testing
- **Reporting**: Management and stakeholder communication
- **Follow-up**: Corrective action tracking

### External Certification
- **Stage 1 Audit**: Documentation review and readiness assessment
- **Stage 2 Audit**: Implementation verification and certification
- **Surveillance Audits**: Ongoing compliance monitoring
- **Recertification**: Triennial certification renewal

## Support and Resources

### Documentation
- [ISO 27001:2022 Standard](https://www.iso.org/standard/27001)
- [ISMS Implementation Guide](docs/isms-procedures.md)
- [Annex A Control Mapping](docs/annex-a-mapping.md)

### Training and Awareness
- **Security Awareness**: General staff training program
- **ISMS Training**: Specialized role-based training
- **Incident Response**: Emergency response procedures
- **Continuous Learning**: Regular security updates

### Professional Services
- **ISMS Consulting**: Implementation guidance and support
- **Risk Assessment**: Professional risk analysis services
- **Internal Audit**: Independent compliance verification
- **Certification Support**: Audit preparation and guidance

## Contributing

Contributions must align with ISO 27001:2022 requirements and organizational security policies.

## License

MIT License - See [LICENSE](LICENSE) file for details.

---

**ISO 27001 Version**: 2022  
**Last Updated**: June 30, 2025  
**ISMS Version**: 1.0  
**Next Review**: December 30, 2025
