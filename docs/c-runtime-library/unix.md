---
title: UNIX | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- unix
dev_langs:
- C++
helpviewer_keywords:
- UNIX
- POSIX compatibility
- POSIX file names
- UNIX, compatibility
ms.assetid: 40792414-7a5b-415d-bfa8-2bfb1ebb3731
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6d0343a7a508e09e3bd7779308cb40972965a716
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46032951"
---
# <a name="unix"></a>UNIX

Wenn Sie Ihre Programme nach UNIX portieren möchten, befolgen Sie folgende Richtlinien:

- Entfernen Sie keine Headerdateien aus dem SYS-Unterverzeichnis. Sie können die SYS-Headerdateien nur an eine andere Stelle verschieben, wenn Sie nicht beabsichtigen, Ihre Programme nach UNIX zu portieren.

- Verwenden Sie die UNIX-kompatiblen Pfadtrennzeichen in Routinen, die Zeichenfolgen für Pfade und Dateinamen als Argumente annehmen. UNIX unterstützt für diesen Zweck nur Schrägstriche (/), wohingegen Win32-Betriebssysteme sowohl umgekehrte Schrägstriche (\\) als auch Schrägstriche (/) unterstützen. Deshalb werden in dieser Dokumentation beispielsweise UNIX-kompatible Schrägstriche als Pfadtrennzeichen in `#include`-Anweisungen verwendet. (Allerdings unterstützt die Befehlsshell des Windows-Betriebssystems, CMD.EXE, keine Schrägstriche in Befehlen, die in der Eingabeaufforderung eingegeben werden.)

- Verwenden Sie ordnungsgemäß funktionierende Pfade und Dateinamen in UNIX, in der die Groß-/Kleinschreibung gilt. Beim FAT-Dateisystem (File Allocation Table) in Win32-Betriebssystemen muss die Groß-/Kleinschreibung nicht berücksichtigt werden. Das NTFS-Dateisystem behält zwar Groß-/Kleinschreibung für Verzeichnislisten bei, ignoriert jedoch die Groß-/Kleinschreibung bei Dateisuchen und anderen Systemvorgängen.

    > [!NOTE]
    >  In dieser Version von Visual C++ wurden UNIX-Kompatibilitätsinformationen aus den Beschreibungen der Funktionen entfernt.

## <a name="see-also"></a>Siehe auch

[Kompatibilität](../c-runtime-library/compatibility.md)