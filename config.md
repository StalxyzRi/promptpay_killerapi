# How to Settings the API Promptpay | [Life Time Version💸]

<img width="128" height="128" alt="image" src="https://github.com/user-attachments/assets/b64b7762-a60b-4cb8-8255-d99bd5fc3a74" /> <img width="128" height="128" alt="image" src="https://github.com/user-attachments/assets/c2590181-d286-4919-bfa7-8af824485a47" />


First : you have to buy or custom by you self in monthy plan

if you want to buy preset : [Click Here👆](https://config.xyz)

<img width="1478" height="620" alt="image" src="https://github.com/user-attachments/assets/809ec565-c1bf-4119-842a-966316ddbf95" />




Free Config and VIP Config can use only Monthy Plan

Premium Config can use in Life Time and Yearly Plan ✨


this is the example.
```json
{
  "meta": {
    "config_version": "3.0.1",
    "environment": "staging",
    "generated_by": "PromptKLZ PaymentConfigGen",
    "generated_on": "2025-10-07T06:30:00+07:00",
    "notes": "Fake payment system config for testing. Edit account.* fields for user-specific values."
  },
  "account": {
    "username": "merchant_azimuth",
    "payment_id": "PMT-7A2F-9C1B",
    "pin": "4829",
    "display_name": "Azimuth Trading Co.",
    "backup_password": "Bkup!2025$Az",
    "email": "ops@azimuth-payments.local",
    "contact_phone": "+66-2-555-0199",
    "locale": "en_TH",
    "timezone": "Asia/Bangkok"
  },
  "endpoints": {
    "api_base": "https://staging-pay.azimuth.local/api/v1",
    "auth_url": "https://staging-auth.azimuth.local/oauth2/token",
    "webhook_url": "https://hooks.azimuth.local/payments",
    "dashboard_url": "https://staging-dashboard.azimuth.local",
    "status_health": "/healthz",
    "transactions_index": "/transactions",
    "refunds_endpoint": "/transactions/refund",
    "payouts_endpoint": "/payouts"
  },
  "security": {
    "jwt_issuer": "azimuth-pay-staging",
    "jwt_expiry_seconds": 3600,
    "encryption": {
      "primary": "AES-256-GCM",
      "secondary": "RSA-2048",
      "key_rotation_days": 90
    },
    "secrets": {
      "api_key_public": "pk_live_stg_9f2a5b1c", 
      "api_key_private": "sk_live_stg_3d7e8a9f", 
      "hmac_secret": "hmac_stg_V4x7qz",
      "webhook_secret": "whsec_stg_Nm2P9"
    },
    "mfa": {
      "enabled": true,
      "methods_allowed": ["totp", "sms", "u2f"],
      "totp_issuer": "Azimuth-Pay"
    },
    "ip_restrictions": {
      "whitelist": ["203.146.0.0/20", "34.87.120.45"],
      "blacklist": ["10.0.0.0/8", "192.168.0.0/16"],
      "fail_open": false
    }
  },
  "currencies": {
    "default": "THB",
    "supported": [
      { "code": "THB", "symbol": "฿", "decimal": 2 },
      { "code": "USD", "symbol": "$", "decimal": 2 },
      { "code": "JPY", "symbol": "¥", "decimal": 0 },
      { "code": "EUR", "symbol": "€", "decimal": 2 }
    ],
    "exchange_rates_source": "https://rates.azimuth.local/latest",
    "fx_tolerance_percent": 0.5
  },
  "limits": {
    "daily_transaction_count": 10000,
    "daily_volume_thb": 10000000,
    "single_transaction_thb_max": 200000,
    "single_transaction_thb_min": 1,
    "chargeback_threshold_percent": 2.0
  },
  "payment_methods": [
    {
      "id": "pm_card_visa",
      "name": "Card - Visa",
      "provider": "cardnet",
      "enabled": true,
      "settlement_delay_days": 2,
      "fee_percent": 2.2,
      "fee_fixed": 3.5,
      "currencies": ["THB","USD","EUR"]
    },
    {
      "id": "pm_card_mc",
      "name": "Card - Mastercard",
      "provider": "cardnet",
      "enabled": true,
      "settlement_delay_days": 2,
      "fee_percent": 2.25,
      "fee_fixed": 3.5,
      "currencies": ["THB","USD","EUR"]
    },
    {
      "id": "pm_qr_promptpay",
      "name": "PromptPay QR",
      "provider": "local_qr",
      "enabled": true,
      "instant_settlement": true,
      "fee_percent": 0.9,
      "fee_fixed": 0.0,
      "currencies": ["THB"]
    },
    {
      "id": "pm_bank_transfer",
      "name": "Bank Transfer (ACH/SWIFT)",
      "provider": "banklink",
      "enabled": true,
      "settlement_delay_days": 1,
      "fee_percent": 0.5,
      "fee_fixed": 10.0,
      "currencies": ["THB","USD"]
    },
    {
      "id": "pm_wallet_local",
      "name": "Azimuth Wallet",
      "provider": "azimuth_wallet",
      "enabled": false,
      "topup_enabled": true,
      "fee_percent": 0.0,
      "fee_fixed": 0.0,
      "currencies": ["THB"]
    }
  ],
  "transactions": [
    {
      "txn_id": "TXN-20251007-0001",
      "amount": 1250.00,
      "currency": "THB",
      "status": "completed",
      "method_id": "pm_qr_promptpay",
      "created_at": "2025-10-06T18:12:44+07:00",
      "customer": {"name": "S. Chaiwat", "email": "chaiwat@example.com"},
      "merchant_ref": "ORD-7781-AZ"
    },
    {
      "txn_id": "TXN-20251007-0002",
      "amount": 499.99,
      "currency": "USD",
      "status": "pending",
      "method_id": "pm_card_visa",
      "created_at": "2025-10-07T01:24:10+07:00",
      "customer": {"name": "Jessica M", "email": "jessica.m@example.net"},
      "merchant_ref": "ORD-7782-AZ"
    },
    {
      "txn_id": "TXN-20251007-0003",
      "amount": 500000,
      "currency": "JPY",
      "status": "failed",
      "method_id": "pm_card_mc",
      "created_at": "2025-10-07T02:00:00+07:00",
      "customer": {"name": "K. Sato", "email": "sato.k@example.jp"},
      "merchant_ref": "ORD-7783-AZ",
      "failure_code": "card_declined"
    },
    {
      "txn_id": "TXN-20251007-0004",
      "amount": 25000,
      "currency": "THB",
      "status": "completed",
      "method_id": "pm_bank_transfer",
      "created_at": "2025-10-05T14:33:21+07:00",
      "customer": {"name": "N. Preecha", "email": "preecha@corp.local"},
      "merchant_ref": "PAYOUT-3342"
    },
    {
      "txn_id": "TXN-20251006-0099",
      "amount": 120.00,
      "currency": "THB",
      "status": "refunded",
      "method_id": "pm_qr_promptpay",
      "created_at": "2025-10-02T09:10:00+07:00",
      "customer": {"name": "A. Siriporn", "email": "siriporn@example.com"},
      "merchant_ref": "ORD-7711-AZ",
      "refund": {"amount": 120.00, "refunded_at": "2025-10-03T11:01:02+07:00"}
    }
  ],
  "batch_rules": {
    "auto_settlement": true,
    "settlement_time_utc": "02:00:00",
    "batch_window_minutes": 15,
    "max_batch_transactions": 5000
  },
  "reconciliation": {
    "enabled": true,
    "provider": "Reconly",
    "cron_schedule": "0 3 * * *",
    "tolerance_percent": 0.1,
    "report_s3_bucket": "s3://azimuth-staging-recon/reports"
  },
  "fees": {
    "default_fee_percent": 1.5,
    "default_fee_fixed": 5.00,
    "tax_percent": 7.0,
    "legacy_fee_overrides": {
      "pm_wallet_local": {"fee_percent": 0.0, "fee_fixed": 0.0}
    }
  },
  "fraud": {
    "enabled": true,
    "provider": "FraudSight",
    "rules": [
      {"id": "FR-01", "desc": "high velocity card attempts", "action": "block"},
      {"id": "FR-02", "desc": "mismatched billing country", "action": "review"},
      {"id": "FR-03", "desc": "blacklisted email domain", "action": "reject"}
    ],
    "score_thresholds": {"block": 90, "review": 60}
  },
  "webhooks": {
    "retries": 3,
    "backoff_seconds": 30,
    "accepted_events": ["payment.succeeded", "payment.failed", "refund.completed", "payout.processed"],
    "default_headers": {"Content-Type": "application/json", "X-PAY-SYSTEM": "Azimuth-Staging"}
  },
  "audit": {
    "log_level": "INFO",
    "retention_days": 365,
    "sensitive_masking": {"card_number": "PAN", "cvv": "***"},
    "external_logging": {"enabled": true, "endpoint": "https://logs.azimuth.local/ingest"}
  },
  "operators": [
    {"id": "op_001", "name": "Nattapong (Ops)", "role": "ops_admin", "contact": "+66-80-111-2233"},
    {"id": "op_002", "name": "Maya (Finance)", "role": "finance_analyst", "contact": "+66-81-999-0101"},
    {"id": "op_003", "name": "Ethan (Security)", "role": "sec_lead", "contact": "+66-2-555-0102"}
  ],
  "connectors": {
    "cardnet": {
      "vendor": "CardNet Ltd.",
      "endpoint": "https://cardnet.stg.azimuth.com/tx",
      "timeout_seconds": 30,
      "max_retries": 2,
      "cert_thumbprint": "3A:5F:9B:18:27"
    },
    "banklink": {
      "vendor": "BankLink Gateway",
      "endpoint": "https://banklink.stg.azimuth.com/transfer",
      "timeout_seconds": 45,
      "max_retries": 1
    }
  },
  "notifications": {
    "email": {
      "from": "no-reply@azimuth.local",
      "support": "support@azimuth.local",
      "templates": {
        "payment_success": "tpl_payment_success_v2",
        "payment_failed": "tpl_payment_failed_v1",
        "refund_processed": "tpl_refund_v1"
      }
    },
    "sms": {
      "enabled": true,
      "provider": "TwilioStub",
      "template_ids": {"otp": "sms_tpl_otp_01"}
    }
  },
  "reports": {
    "daily_summary": {"enabled": true, "deliver_to": ["finance@azimuth.local", "ops@azimuth.local"]},
    "weekly_settlement": {"enabled": true, "deliver_to": ["settlement@azimuth.local"]},
    "formats": ["pdf", "csv", "json"]
  },
  "maintenance": {
    "maintenance_mode": false,
    "announce_window_minutes": 30,
    "allowed_ips_during_maintenance": ["203.146.5.10"]
  },
  "legacy": {
    "legacy_api_support": true,
    "legacy_keys": [
      "LEGACY-KEY-A-2020",
      "LEGACY-KEY-B-2021"
    ],
    "migrate_to_new_schema": "2026-01-01"
  },
  "features": {
    "dynamic_pricing": false,
    "instant_refunds": true,
    "one_click_checkout": true,
    "3ds_force": false
  },
  "testing": {
    "sandbox_cards": [
      {"number": "4242424242424242", "cvv": "123", "expiry": "12/26"},
      {"number": "4000000000000002", "cvv": "456", "expiry": "11/24"}
    ],
    "simulate_latency_ms": 120,
    "simulate_failure_rate_percent": 0.2
  },
  "translations": {
    "en": {"payment_success": "Payment completed", "payment_failed": "Payment failed"},
    "th": {"payment_success": "ชำระเงินเรียบร้อย", "payment_failed": "ชำระเงินไม่สำเร็จ"}
  },
  "service_health": {
    "last_checked": "2025-10-07T06:29:55+07:00",
    "components": {
      "database": {"status": "ok", "response_ms": 32},
      "redis_cache": {"status": "ok", "response_ms": 4},
      "worker_queue": {"status": "degraded", "pending_jobs": 98}
    }
  },
  "sample_logs": [
    {"ts": "2025-10-07T06:00:01+07:00", "level": "INFO", "msg": "worker started", "ctx": {"pid": 4421}},
    {"ts": "2025-10-07T06:05:12+07:00", "level": "WARN", "msg": "delayed webhook delivery", "ctx": {"webhook_id": "wh_212"}},
    {"ts": "2025-10-07T06:10:30+07:00", "level": "INFO", "msg": "settlement batch completed", "ctx": {"batch_id": "BATCH-20251007-01"}}
  ],
  "dev_options": {
    "enable_debug_endpoints": false,
    "feature_flags": {
      "ff_dynamic_cv_check": false,
      "ff_new_onboarding_flow": true
    },
    "mock_mode": {
      "enabled": true,
      "mock_user_ids": ["test_user_01", "test_user_02"]
    }
  },
  "integrations": {
    "accounting": {"enabled": true, "provider": "LedgerPlus", "endpoint": "https://ledger.stg.azimuth.local/ingest"},
    "crm": {"enabled": false, "provider": "CRMero"},
    "tax_provider": {"enabled": true, "provider": "TaxMate", "region_map": {"TH": "TAX-TH"}}
  },
  "slo": {
    "uptime_target_percent": 99.95,
    "p95_response_ms": 180,
    "p99_response_ms": 450
  },
  "storage": {
    "object_store": {"provider": "minio", "bucket_prefix": "azimuth-stg"},
    "db_replication": {"read_replicas": 2, "replica_lag_seconds": 0.8}
  },
  "email_templates": {
    "welcome": {"subject": "Welcome to Azimuth Payments", "id": "tpl_welcome_v1"},
    "invoice": {"subject": "Your invoice", "id": "tpl_invoice_v4"}
  },
  "payouts": {
    "next_run": "2025-10-08T02:00:00+07:00",
    "cutoff_hour": 18,
    "min_payout_thb": 100.0,
    "payout_providers": ["banklink", "swift"]
  },
  "monitoring": {
    "prometheus": {"scrape_interval": "15s", "endpoint": "http://prom.stg.azimuth.local:9090"},
    "alerting": {"pagerduty": {"enabled": true, "service_key": "PD-SVC-STG-88"}}
  },
  "deployment": {
    "strategy": "rolling",
    "max_surge": "25%",
    "max_unavailable": "10%",
    "docker_image": "azimuth/payments:staging-3.0.1"
  },
  "mock_dataset": {
    "customers": [
      {"id": "cust_001", "name": "Siriwat P.", "tier": "standard"},
      {"id": "cust_002", "name": "Nicha Y.", "tier": "gold"},
      {"id": "cust_003", "name": "Global Import Co.", "tier": "enterprise"}
    ]
  },
  "cli": {
    "version": "0.9.7-stg",
    "last_update_check": "2025-10-01T04:00:00+07:00",
    "auto_update": false
  },
  "notes": "All values are fake and for testing only. Do not use these in production.",
  "changelogs": [
    {"v": "3.0.1", "date": "2025-10-01", "desc": "staging config schema revision"},
    {"v": "3.0.0", "date": "2025-08-15", "desc": "added multi-currency support"}
  ]
}

```
