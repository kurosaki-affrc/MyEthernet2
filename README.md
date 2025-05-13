このライブラリはWiz550ioの機能を有効に活用するためにEthernet2ライブラリ(https://github.com/adafruit/Ethernet2 )を改変したものです。
Wiz550ioのROMに書き込まれた内蔵MACアドレス設定機能を有効化しています。
MACアドレスをソースコード上にハードコーディングしなくても自動的に正しいMACアドレスが割り当てられます。

元々のEthernet2ライブラリはArduinoにおいてW5500を搭載したイーサネット通信機能を動作させるためのものです。
Ver1.0.3とVer1.0.4以降ではROMにMACアドレスが書き込まれたW5500に対する動作に違いがあります。
Ver1.0.3では内蔵MACアドレスを利用できます。これはVer1.0.3の隠し機能として実装されていました。
しかし、Ver1.0.4以降では内蔵MACアドレスが無視されます。
この問題はROMにMACアドレスが書き込まれたWiz550ioを利用するときに発生します。
(Ethernet Shield2ではROMにMACアドレスが書かれていません。ステッカーに記載されているだけです)

Ethernet2ライブラリを最新版にアップデートすると内蔵MACアドレスを利用できなくなります。
この問題を解決するため分岐したのがこのMyEthernet2ライブラリです。
Ethernet2ライブラリと共存するために全てのファイル名を書き換えてあります。

Raspberry Pi PICOで使用したとき、低い頻度でフリーズする問題を解決しました。

既知の問題
コンパイルのときに警告が出ますが実害は無いようです。
過去のバージョンにあった1回しか初期化できない問題は解決されました。



This library is a modified version of the Ethernet2 library (https://github.com/adafruit/Ethernet2 ) to effectively utilize the functions of Wiz550io.
It enables the built-in MAC address setting function written in ROM of Wiz550io.
The correct MAC address is automatically assigned without having to hard-code the MAC address into the source code.

The original Ethernet2 library was designed to run the Ethernet communication function with W5500 on Arduino.
Ver1.0.3 and Ver1.0.4 or later have differences in operation for W5500 with MAC address written in ROM.
Ver1.0.3 can use the built-in MAC address. This was implemented as a hidden feature in Ver1.0.3.
However, Ver1.0.4 and later ignore the built-in MAC address.
This problem occurs when using Wiz550io with MAC address written in ROM.
(Ethernet Shield2 does not have a MAC address written in ROM. It is only written on a sticker.)

If the Ethernet2 library is updated to the latest version, the built-in MAC address will not be available.
To solve this problem, we branched out to this MyEthernet2 library.
All file names have been rewritten to coexist with the Ethernet2 library.

Resolved a problem with low frequency freezes when used with Raspberry Pi PICO.

Known problems

A warning message appears at compile time, but it does not seem to cause any harm.
The problem that the library can be initialized only once, which existed in past versions, has been resolved.

-----------------------------------------------------------------------------------------------------
License
Copyright (c) 2009-2016 Arduino LLC. All right reserved.

This library is free software; you can redistribute it and/or modify it under the terms of the GNU Lesser General Public License as published by the Free Software Foundation; either version 2.1 of the License, or (at your option) any later version.

This library is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU Lesser General Public License for more details.

You should have received a copy of the GNU Lesser General Public License along with this library; if not, write to the Free Software Foundation, Inc., 51 Franklin St, Fifth Floor, Boston, MA 02110-1301 USA

