---
title: Compiler-Controlled LINK Options
ms.date: 11/04/2016
f1_keywords:
- link
helpviewer_keywords:
- LINK tool [C++], compiler-controlled options
- linker [C++], CL compiler control
- linking [C++], affected by CL features
- cl.exe compiler [C++], features that affect linking
- cl.exe compiler [C++], controlling linker
ms.assetid: e4c03896-c99c-4599-8502-e0f4bebe69d0
ms.openlocfilehash: 21d0baccaf74fc08bb110b0ae9f8b7dc108abd6b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50561575"
---
# <a name="compiler-controlled-link-options"></a>Compiler-Controlled LINK Options

Der CL-Compiler ruft automatisch LINK aus, es sei denn, Sie geben die Option. CL stellt eine gewisse Kontrolle über den Linker über Befehlszeilenoptionen und Argumente bereit. Die folgende Tabelle enthält die Funktionen in der Berechnungsliste, die Verknüpfung zu beeinflussen.

|CL-Spezifikation|CL-Aktion, die Verknüpfung wirkt sich auf|
|----------------------|---------------------------------|
|Eine beliebige Dateinamenerweiterung als c, .cxx, cpp oder DEF|Übergibt einen Dateinamen als Eingabe für den LINK|
|*FileName*DEF|Übergibt/DEF:*Filename*DEF|
|/ F*Anzahl*|Übergibt/Stack:*Anzahl*|
|/ Fd*Dateiname*|Übergibt der/PDB:*Dateiname*|
|/ FE*Dateiname*|Übergibt/OUT:*Dateiname*|
|/ FM*Dateiname*|Übergibt/Map:*Dateiname*|
|/Gy|Erstellt von Paketfunktionen (COMDATs); Aktiviert Funktionslevel-linking.|
|/LD|/ DLL übergeben|
|/LDd|/ DLL übergeben|
|/link|Übergibt den Rest der Befehlszeile Link|
|/ MD oder/MT|Wird einen Standard-Bibliotheksnamen in der OBJ-Datei|
|/ MDd "oder" / MTd|Platziert einen Standard-Bibliotheksnamen in der OBJ-Datei an. Definiert das Symbol **_DEBUG**|
|/nologo|/ Nologo übergibt|
|"/ Zd"|Übergibt "/ Debug"|
|"/ Zi" oder "/ Z7"|Übergibt "/ Debug"|
|/Zl|Lässt Standardbibliotheksname in OBJ-Datei|

Weitere Informationen finden Sie unter [Compileroptionen](../../build/reference/compiler-options.md).

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)