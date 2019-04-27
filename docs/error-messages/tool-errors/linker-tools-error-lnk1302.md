---
title: Linkertoolfehler LNK1302
ms.date: 11/04/2016
f1_keywords:
- LNK1302
helpviewer_keywords:
- LNK1302
ms.assetid: aea3c753-c2c4-4249-bbc3-f2d4f0164b5e
ms.openlocfilehash: c3b1117b31db4759b385943323a581da7a58f0c4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160444"
---
# <a name="linker-tools-error-lnk1302"></a>Linkertoolfehler LNK1302

nur die Verknüpfung sicherer .netmodules unterstützt; Datei .netmodule kann nicht verknüpft

Eine NETMODULE-Datei (kompiliert mit **/ln**) an den Linker den Versuch eines Benutzers zum Aufrufen der MSIL-Verknüpfung übergeben wurde.  Ein C++-Modul ist gültig für MSIL verknüpfen, wenn die Kompilierung mit **/CLR: safe**.

Um diesen Fehler zu beheben, kompilieren Sie mit **/CLR: safe** MSIL-linking aktivieren, oder übergeben die **"/ CLR"** oder **/CLR: pure** OBJ-Datei an den Linker anstelle des Moduls.

Weitere Informationen finden Sie unter

- [/LN (MSIL-Modul erstellen)](../../build/reference/ln-create-msil-module.md)

- [.NETMODULE-Dateien als Eingabe für den Linker](../../build/reference/netmodule-files-as-linker-input.md)