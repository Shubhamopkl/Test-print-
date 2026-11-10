# ScanPrint Phase 1–6

This build keeps the glassmorphism kiosk design and adds a phase-wise print workflow.

## Included
- Phase 1: upload, PDF page count, live pricing, UPI QR flow, Razorpay hook, token/status, owner dashboard, cleanup.
- Phase 2: PDF/office/image uploads, LibreOffice conversion hook, B&W/colour, 2-in-1/4-in-1, page range, preview/auto-crop/blank-page options, pricing controls.
- Phase 3: release PIN, cancel/refund workflow, notification provider hook, print status.
- Phase 4: photo/ID services, binding, lamination, stapling.
- Phase 5: reports/dashboard data, inventory, printer status, staff accounts, auto-print-agent status hook.
- Phase 6: `shop_id` on orders/settings, shop selector and shop creation, multi-shop-ready API structure.

## Important production notes
- Current data store is JSON (`data/db.json`) for a simple Render deployment. For a multi-shop production deployment, move this schema to PostgreSQL.
- Razorpay needs `RAZORPAY_KEY_ID` and a secure server-side payment verification/order-creation implementation before accepting real payments.
- UPI QR needs `UPI_VPA` and `UPI_PAYEE_NAME`.
- Word/PPT/Excel conversion needs LibreOffice installed on the server.
- WhatsApp/SMS needs a provider and credentials.
- Silent USB/Wi-Fi printing needs a local print agent; browser printing is supported in this web build.
- Do not expose payment/API secrets in frontend code.
