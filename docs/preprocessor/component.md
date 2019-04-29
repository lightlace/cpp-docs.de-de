---
title: component
ms.date: 04/08/2019
f1_keywords:
- vc-pragma.component
- component_CPP
helpviewer_keywords:
- component pragma
- pragmas, component
ms.assetid: 7b66355e-3201-4c14-8190-f4a2a81a604a
ms.openlocfilehash: 4870860650a39d27639ad18100ba37ba14aa15c0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62366913"
---
# <a name="component"></a>component

Die Erfassung von Browserinformationen oder Abhängigkeitsinformationen aus Quelldateien gesteuert.

## <a name="syntax"></a>Syntax

> **#pragma Component (Browser** { **auf** | **aus** } [**,** **Verweise** [**,** *Namen* ]] **)** \
> **#pragma component( minrebuild, on** | **off )** \
> **#pragma component( mintypeinfo, on** | **off )**

## <a name="remarks"></a>Hinweise

### <a name="browser"></a>Browser

Sie können das Sammeln aktivieren oder deaktivieren, und Sie können angeben, dass bestimmte Namen beim Sammeln von Informationen ignoriert werden.

Die Aktivierung oder Deaktivierung steuert das Sammeln von Browserinformationen ab dem nächsten Pragma. Zum Beispiel:

```cpp
#pragma component(browser, off)
```

Dieser Code stoppt das Sammeln von Browserinformationen durch den Compiler.

> [!NOTE]
> So aktivieren auf das Sammeln von Browserinformationen mit diesem Pragma [Browseinformationen muss zunächst aktiviert werden](../build/reference/building-browse-information-files-overview.md).

Die `references` Option kann verwendet werden, mit oder ohne die *Namen* Argument. Mithilfe von `references` ohne *Namen* aktiviert oder deaktiviert das Sammeln von verweisen (andere Browserinformationen weiterhin gesammelt werden, jedoch werden). Zum Beispiel:

```cpp
#pragma component(browser, off, references)
```

Dieser Code stoppt das Sammeln von Verweisinformationen durch den Compiler.

Mithilfe von `references` mit *Namen* und `off` wird verhindert, dass Verweise auf *Namen* im Suchfenster Informationen angezeigt werden. Verwenden Sie die folgende Syntax, um Namen und Typen zu ignorieren, die für Sie nicht relevant sind, und die Größe von Browserinformationsdateien zu reduzieren. Zum Beispiel:

```cpp
#pragma component(browser, off, references, DWORD)
```

ignoriert Verweise auf DWORD ab diesem Punkt an. Sie können das Sammeln von Verweisen auf DWORD wieder über aktivieren `on`:

```cpp
#pragma component(browser, on, references, DWORD)
```

Dies ist die einzige Möglichkeit, setzen Sie fort, das Sammeln von Verweisen auf *Namen*; Sie müssen explizit aktivieren, auf einem *Namen* , die Sie deaktiviert haben.

Um zu verhindern, dass den Präprozessor erweitert *Namen* (z. B. das Erweitern von NULL, 0), platzieren Sie Anführungszeichen:

```cpp
#pragma component(browser, off, references, "NULL")
```

### <a name="minimal-rebuild"></a>Minimale Neuerstellung

Die veraltete [/GM (minimale Neuerstellung aktivieren)](../build/reference/gm-enable-minimal-rebuild.md) Funktion erfordert den Compiler zum Erstellen und speichern C++ Klasse Abhängigkeitsinformationen, wofür Speicherplatz benötigt. Um Speicherplatz zu sparen, können Sie `#pragma component( minrebuild, off )` jedes Mal, wenn Sie möchten keine Abhängigkeitsinformationen z. B. in unveränderlichen Headerdateien zu sammeln. Fügen Sie `#pragma component(minrebuild, on)` nach dem Sichern der unveränderlicher Klassen, aktivieren Sie die Auflistung von Abhängigkeiten auf.

### <a name="reduce-type-information"></a>Reduzieren von Typinformationen

Die `mintypeinfo` Option reduziert die Debuginformationen für den angegebenen Bereich. Diese Informationen haben einen beträchtlichen Umfang und wirken sich auf PDB- und OBJ-Dateien aus. Sie können Klassen und Strukturen im mintypeinfo-Bereich nicht debuggen. Die Verwendung der mintypeinfo-Option kann hilfreich sein, um die folgende Warnung zu vermeiden:

```cmd
LINK : warning LNK4018: too many type indexes in PDB "filename", discarding subsequent type information
```

Weitere Informationen finden Sie unter den [/GM (minimale Neuerstellung aktivieren)](../build/reference/gm-enable-minimal-rebuild.md) -Compileroption.

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)