import qrcode
import os
from datetime import datetime

# Data to encode
data = "053129~0891278133~1~1~7~0010160~12~0080030~24~0080040~36~0103406~36"

# Directory to save QR codes
output_dir = "qrcodes"
os.makedirs(output_dir, exist_ok=True)

# Timestamped filename
timestamp = datetime.now().strftime("%Y%m%d_%H%M%S")
filename = f"barcode_{timestamp}.png"
output_path = os.path.join(output_dir, filename)

# QR Code config
qr = qrcode.QRCode(
    version=5,
    error_correction=qrcode.constants.ERROR_CORRECT_M,
    box_size=10,
    border=2,
)

# Add data and create image
qr.add_data(data)
qr.make(fit=True)
img = qr.make_image(fill_color="black", back_color="white")

# Save image
img.save(output_path)

print(f"QR Code saved to {output_path}")
