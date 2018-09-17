---
title: Compilergesteuerte Linkoptionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- link
dev_langs:
- C++
helpviewer_keywords:
- LINK tool [C++], compiler-controlled options
- linker [C++], CL compiler control
- linking [C++], affected by CL features
- cl.exe compiler [C++], features that affect linking
- cl.exe compiler [C++], controlling linker
ms.assetid: e4c03896-c99c-4599-8502-e0f4bebe69d0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ee952fe5152d98aa33c4ef7e98f8a2eb3ef077be
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45726426"
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