---
title: /BIND
ms.date: 11/04/2016
f1_keywords:
- /bind
helpviewer_keywords:
- -BIND editbin option
- entry points, addresses
- BIND editbin option
- entry points
- /BIND editbin option
- import address table
ms.assetid: 3772b330-1868-4c90-857d-c31faa867982
ms.openlocfilehash: e8ba0a5f0235c8771567e4e43172bdf8c81c99a2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62295031"
---
# <a name="bind"></a>/BIND

```
/BIND[:PATH=path]
```

## <a name="remarks"></a>Hinweise

Diese Option wird die Adressen der Einstiegspunkte in die Importadresstabelle für eine ausführbare Datei oder DLL an. Verwenden Sie diese Option, um die Ladezeit eines Programms zu reduzieren.

Geben Sie die ausführbare Datei des Programms und die-DLLs in den *Dateien* Argument in der EDITBIN-Befehlszeile. Der optionale *Pfad*  /BIND Argument gibt den Speicherort der DLLs, die von den angegebenen Dateien verwendet. Trennen Sie mehrere Verzeichnisse durch ein Semikolon (**;**). Wenn *Pfad* nicht angegeben ist, EDITBIN durchsucht, die in der PATH-Umgebungsvariablen angegebenen Verzeichnisse. Wenn *Pfad* angegeben ist, EDITBIN ignoriert der PATH-Variablen.

Standardmäßig legt das Ladeprogramm die Adressen von Einstiegspunkten, beim Laden eines Programms. Die Zeitspanne, die dieser Vorgang dauert hängt, von der Anzahl der DLLs und die Anzahl von Einstiegspunkten, die im Programm verwiesen wird. Wenn ein Programm mit/BIND geändert wurde, und die Basisadressen für die ausführbare Datei und die DLLs nicht in Konflikt mit DLLs, die bereits geladen sind, muss das Betriebssystem nicht diese Adressen festlegen. In einer Situation, in dem die Dateien nicht ordnungsgemäß basieren, das Betriebssystem die DLLs des Programms verschiebt und berechnet die Einstiegspunkt Adressen, die zur Ladezeit des Programms hinzugefügt.

## <a name="see-also"></a>Siehe auch

[EDITBIN-Optionen](editbin-options.md)
