---
title: Schwerwiegender Fehler C1352
ms.date: 11/04/2016
f1_keywords:
- C1352
helpviewer_keywords:
- C1352
ms.assetid: d044e8b0-b6ef-4d57-8eb5-6254071be707
ms.openlocfilehash: fbba87cea05d666d6dc3a385ca1fe52e143fdb5a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62329724"
---
# <a name="fatal-error-c1352"></a>Schwerwiegender Fehler C1352

Ungültige oder beschädigte MSIL in "Funkion"-Funktion aus Modul "Datei".

Eine NETMODULE-Datei wurde an den Compiler übergeben, aber der Compiler hat eine Beschädigung in der Datei erkannt.  Bitten Sie die Person, die die NETMODULE-Datei erstellt hat, diese zu überprüfen.

Der Compiler überprüft NETMODULE-Dateien nicht auf alle Arten von Beschädigung.  Er prüft jedoch, ob alle Steuerelementpfade in einer Funktion eine return-Anweisung enthalten.

Weitere Informationen finden Sie unter [NETMODULE-Dateien als Eingabe für den Linker](../../build/reference/netmodule-files-as-linker-input.md).