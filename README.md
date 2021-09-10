# android导入Telegram表情包Intent格式

```
private static final String CREATE_STICKER_PACK_ACTION = "org.telegram.messenger.CREATE_STICKER_PACK";
private static final String CREATE_STICKER_PACK_EMOJIS_EXTRA = "STICKER_EMOJIS";
private static final String CREATE_STICKER_PACK_IMPORTER_EXTRA = "IMPORTER";

public void importSticker(AppCompatActivity pActivity, ArrayList<Uri> stickers, ArrayList<String> emojis) {
  Intent intent = new Intent(CREATE_STICKER_PACK_ACTION);
  intent.putExtra(Intent.EXTRA_STREAM, stickers);
  intent.putExtra(CREATE_STICKER_PACK_IMPORTER_EXTRA, pActivity.getPackageName());
  intent.putExtra(CREATE_STICKER_PACK_EMOJIS_EXTRA, emojis);
  intent.setType("image/*");

  try {
    pActivity.startActivity(intent);
    } catch (Exception e) {
      e.printStackTrace();
    }
}
```
