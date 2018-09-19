---
title: Linkertoolfehler Lnk1302 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1302
dev_langs:
- C++
helpviewer_keywords:
- LNK1302
ms.assetid: aea3c753-c2c4-4249-bbc3-f2d4f0164b5e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3dc85b37d58e12602c02c2207c1f38bda9344e59
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46045509"
---
# <a name="linker-tools-error-lnk1302"></a>Linkertoolfehler LNK1302

nur die Verknüpfung sicherer .netmodules unterstützt; Datei .netmodule kann nicht verknüpft

Eine NETMODULE-Datei (kompiliert mit **/ln**) an den Linker den Versuch eines Benutzers zum Aufrufen der MSIL-Verknüpfung übergeben wurde.  Ein C++-Modul ist gültig für MSIL verknüpfen, wenn die Kompilierung mit **/CLR: safe**.

Um diesen Fehler zu beheben, kompilieren Sie mit **/CLR: safe** MSIL-linking aktivieren, oder übergeben die **"/ CLR"** oder **/CLR: pure** OBJ-Datei an den Linker anstelle des Moduls.

Weitere Informationen finden Sie unter

- [/LN (MSIL-Modul erstellen)](../../build/reference/ln-create-msil-module.md)

- [.NETMODULE-Dateien als Eingabe für den Linker](../../build/reference/netmodule-files-as-linker-input.md)