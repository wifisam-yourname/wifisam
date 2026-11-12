import os
import zipfile

def create_zip_from_folder(folder_path, output_zip_name):
    """
    دالة لضغط مجلد كامل (مثل مجلد www) إلى ملف zip
    """
    with zipfile.ZipFile(output_zip_name, 'w', zipfile.ZIP_DEFLATED) as zipf:
        # المشي عبر جميع المجلدات والملفات داخل المسار
        for root, dirs, files in os.walk(folder_path):
            for file in files:
                # المسار الكامل للملف
                file_path = os.path.join(root, file)
                # المسار النسبي داخل ملف الـ zip لكي يحافظ على هيكل المجلدات
                arcname = os.path.relpath(file_path, start=os.path.join(folder_path, '..'))
                zipf.write(file_path, arcname)
                print(f"تمت إضافة: {arcname}")

    print(f"\nتم إنشاء الملف المضغوط بنجاح باسم: {output_zip_name}")

# مثال على الاستخدام:
# تأكد من أن مجلد 'www' موجود في نفس مسار هذا الكود
if __name__ == "__main__":
    target_folder = "www"  # اسم المجلد المراد ضغطه
    zip_filename = "raawi-apk.zip"   # اسم ملف الـ zip الناتج
    
    if os.path.exists(target_folder):
        create_zip_from_folder(target_folder, zip_filename)
    else:
        print(f"المجلد '{target_folder}' غير موجود، يرجى التأكد من المسار.")
