[EN](./README.md) | **CN**
# HoYo 新增音乐提取工具

利用 Hdiff 对 pck 文件进行补丁处理，随后检索文件以查找新增音乐，并将其解码为 Nero AAC (`.m4a`) 格式。

### 使用方法

1. 将 `.hdiff` 文件放入 `./Hdiff Files` 文件夹，并将所有原始游戏 pck 文件放入 `./Original Game Files` 文件夹。
2. 运行脚本：`python main.py`。
3. 如果没有 `.hdiff` 文件，但拥有想要进行比对和筛选的新版游戏 pck 文件，请将所有新文件放入 `./New Game Files` 文件夹，并运行脚本：`python main.py --no-hdiff`。
4. 若需从 PCK 文件文件夹中提取**所有**音频（无需比对），请运行 `python main.py --full "path/to/pck/folder"`。也可以直接运行 `python main.py --full`，随后根据提示输入路径。
5. 如果任何必需的文件夹为空，脚本将提示您输入路径。支持外部绝对路径（例如 `D:\Games\Genshin\Audio`）。

---

### 注意事项

输出编码参数设定为 `neroAacEnc -q 0.69`，因为 WAV 格式浪费磁盘空间，而 MP3 和 OGG 格式音质较差。请注意，输出完成后，`./Temp` 文件夹下的所有临时文件将被删除。 ---

### 特别鸣谢

- [Nero AAC - Hydrogenaudio Knowledgebase](https://wiki.hydrogenaud.io/index.php?title=Nero_AAC#neroAacEnc)
- [PseudoResonance/Genshin-Impact-New-Music-Unpacker: 解包游戏音频 Wwise 文件 (pck, bnk) (github.com)](https://github.com/PseudoResonance/Genshin-Impact-New-Music-Unpacker)
- [Vextil/Wwise-Unpacker: 解包游戏音频 Wwise 文件 (pck, bnk) (github.com)](https://github.com/Vextil/Wwise-Unpacker)
- [HoYo-New-Music-Extractor: 原始源代码 (github.com)](https://github.com/paimoooon/HoYo-New-Music-Extractor)