# MDPro3 Custom Cards — Build & Share Packs (`.ypk`)

A short, practical guide to package your custom Yu-Gi-Oh! cards for **MDPro3**, upload them, and let others download them in-game.

---

## Table of Contents

* [1) Prerequisites](#1-prerequisites)
* [2) (Optional) Render your cards in MDPro3](#2-optional-render-your-cards-in-mdpro3)
* [3) Build your pack with the Empty Model](#3-build-your-pack-with-the-empty-model)
* [4) Upload your pack](#4-upload-your-pack)
* [5) Install & use in MDPro3](#5-install--use-in-mdpro3)
* [FAQ & Tips](#faq--tips)

---

## 1) Prerequisites

Have these ready:

* **Artworks** (not rendered; raw artwork files)
* **Scripts** (your Lua card scripts)
* **`.cdb`** (SQLite database containing your card data)

---

## 2) (Optional) Render your cards in MDPro3

If you want to ship rendered images (recommended):

1. Place your **artworks** in the folder **`Art2`** (MDPro3 uses this when rendering).
2. Build a deck with your custom cards.
3. In MDPro3, open any card in that deck → **Save Image** → **Current Deck’s Card Images**.
4. Your rendered images will be output to:

   ```
   root\MDPro3\Picture\CardGenerated
   ```

---

## 3) Build your pack with the Empty Model

1. Download the **Empty Model** (`.ypk`)
   👉 [Empty Model.ypk](https://github.com/ElderLich/MDPro3---Custom-Cards/raw/refs/heads/main/000.%20Empty/Empty%20Model.ypk)

2. A **`.ypk`** is just a zip container. Open it with **WinRAR** or **7-Zip** and place your files in the following structure:

```
MyCustomPack.ypk
├─ pack/
│  └─ <your_deck>.ydk                  # optional: a deck containing your custom cards
├─ pics/
│  └─ <rendered_card_images>.png       # rendered cards from Step 2
├─ script/
│  └─ <your_card_scripts>.lua          # your custom scripts
├─ test-strings.conf                   # defines your custom Archetype strings
└─ custom.cdb                          # your custom .cdb (name can be anything)
```

* **`pack/`** → drop a `.ydk` if you want to include a demo deck.
* **`pics/`** → place your **rendered** card images.
* **`script/`** → place your **Lua** scripts.
* **`test-strings.conf`** → contains your custom **Archetype** strings.
* **`custom.cdb`** → your database file (any filename is fine).

*Screenshot (structure example):*
![Pack structure example](https://media.discordapp.net/attachments/1410334156168232991/1410340930497548439/image.png?ex=68cefc58\&is=68cdaad8\&hm=8eabe91a949a2f4c8a695a74a23f1479ef312e6a8e6befcfcb02924ed146fe3a&=\&format=webp\&quality=lossless)

---

## 4) Upload your pack

You have two options to share your `.ypk`:

* **Make a Pull Request** to the main repo:
  👉 [https://github.com/ElderLich/MDPro3---Custom-Cards/tree/main](https://github.com/ElderLich/MDPro3---Custom-Cards/tree/main)
* **Upload via the browser** (clone the repo or add files directly on GitHub).

**Naming scheme suggestion:** create a new numbered folder (helps ordering):

* `002. TestXXX/`
* `003. BEWD/`
* etc.

Place your `.ypk` file inside that folder.

---

## 5) Install & use in MDPro3

To allow MDPro3 to fetch your pack, you **must** share the **RAW link** to your `.ypk` file (other hosts like Google Drive won’t work for in-game downloads).

**Example RAW link:**

```
https://github.com/ElderLich/MDPro3---Custom-Cards/raw/refs/heads/main/001.%20Diabound%20-%20Zorc/Zorc-Diabound.ypk
```

*Screenshots (download flow):*

* **MDPro3 → SETTINGS → EXPANSIONS → Download Custom Card Pack**
  ![Open download panel](https://media.discordapp.net/attachments/1410334156168232991/1410344476844494909/Screenshot_2025-08-27_212447.png?ex=68ceffa6\&is=68cdae26\&hm=1819c33921d23877628211562c1df50b67cc5f7753c8b98095b72bce50550941&=\&format=webp\&quality=lossless)

* **Paste the RAW link**
  ![Paste raw link](https://media.discordapp.net/attachments/1410334156168232991/1410344976382038128/image.png?ex=68cf001d\&is=68cdae9d\&hm=1478faad2dd0d460c2e1cc05e8a2aa3653fcd1c03bfc3ebdb47a629ad869e4c1&=\&format=webp\&quality=lossless\&width=1672\&height=587)

* **Download begins**
  ![Download progress](https://media.discordapp.net/attachments/1410334156168232991/1410345191927451669/image.png?ex=68cf0050\&is=68cdaed0\&hm=ffc0bbd4237cb7d204837d7986da01acdbf09dd706ae8a5cf0b5c50d699c9566&=\&format=webp\&quality=lossless\&width=1672\&height=634)

* **Cards available in search / use the “Custom” filter**
  ![Search custom cards](https://media.discordapp.net/attachments/1410334156168232991/1410345356528582820/image.png?ex=68cf0077\&is=68cdaef7\&hm=6413feacfca0410188b793358c71b14e86e5e6343024969132b87f49307062e6&=\&format=webp\&quality=lossless\&width=1672\&height=221)

  ![Filter by Custom](https://media.discordapp.net/attachments/1410334156168232991/1410345797220040854/image.png?ex=68cf00e1\&is=68cdaf61\&hm=872a4dbdf0c3eb1b3e5ae2cd2a227c3f6c715f0ba9156d286fcbda8ef048299b&=\&format=webp\&quality=lossless\&width=1672\&height=191)

  ![Use in deckbuilding](https://media.discordapp.net/attachments/1410334156168232991/1410345842807930940/image.png?ex=68cf00eb\&is=68cdaf6b\&hm=536188034d5f41ecc6e72ce32dc98368858a809f66094506b134d1202c35ea66&=\&format=webp\&quality=lossless)

**Happy Dueling with Custom Cards!**

---

## FAQ & Tips

* **Why RAW links?**
  MDPro3’s downloader expects a direct file response. GitHub’s **Raw** URL serves the file directly; many cloud hosts add HTML wrappers that break downloads.

* **My pack doesn’t download. What should I check?**

  * Make sure you used the **Raw** link (right-click “Raw” → Copy link).
  * Confirm the `.ypk` contains the correct folder names: `pack/`, `pics/`, `script/`.
  * If you included a deck, ensure it’s a valid `.ydk` in `pack/`.

* **Do I need rendered images?**
  No, but shipping **rendered** images in `pics/` gives your cards proper visuals out of the box.