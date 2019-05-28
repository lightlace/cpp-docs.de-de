---
title: Ändern von WINVER und _WIN32_WINNT
ms.date: 09/04/2017
helpviewer_keywords:
- WINVER in an upgraded Visual Studio C++ project
- _WIN32_WINNT in an upgraded Visual Studio C++ project
ms.assetid: 6a1f1d66-ae0e-48a7-81c3-524d8e8f3447
ms.openlocfilehash: a624118bdd192c5ec677be81f0b410d2392e62e9
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2019
ms.locfileid: "65449072"
---
# <a name="modifying-winver-and-win32winnt"></a>Ändern von WINVER und _WIN32_WINNT

Visual C++ unterstützt nicht mehr die Zielversionen Windows 95, Windows 98, Windows ME, Windows NT oder Windows 2000. Wenn das **WINVER** - oder **_WIN32_WINNT** -Makro einer dieser Versionen von Windows zugewiesen ist, müssen Sie die Makros ändern. Wenn Sie ein Projekt aktualisieren, das mit einer früheren Version von Visual C++ erstellt wurde, werden möglicherweise Kompilierungsfehler im Zusammenhang mit dem **WINVER** - oder **_WIN32_WINNT** -Makro angezeigt, wenn dieses einer Version von Windows zugewiesen ist, die nicht mehr unterstützt wird.

## <a name="remarks"></a>Anmerkungen

Um die Makros in einer Headerdatei (z. B. targetver.h, die enthalten ist, wenn Sie ein Projekt für Windowns erstellen) zu ändern, fügen Sie die folgenden Zeilen hinzu.

```C
#define WINVER 0x0A00
#define _WIN32_WINNT 0x0A00
```

Dies betrifft das Betriebssystem Windows 10. Diese Werte sind in der Windows-Headerdatei SDKDDKVer.h, aufgeführt, die auch Makros für jede Windows-Version definiert. Sie sollten die #define-Anweisung hinzufügen, bevor Sie SDKDDKVer.h einfügen. Dies sind die Zeilen aus der Windows-10-Version von SDKDDKVer.h, die die Werte für jede Version von Windows codieren:

```C
//
// _WIN32_WINNT version constants
//
#define _WIN32_WINNT_NT4                    0x0400 // Windows NT 4.0
#define _WIN32_WINNT_WIN2K                  0x0500 // Windows 2000
#define _WIN32_WINNT_WINXP                  0x0501 // Windows XP
#define _WIN32_WINNT_WS03                   0x0502 // Windows Server 2003
#define _WIN32_WINNT_WIN6                   0x0600 // Windows Vista
#define _WIN32_WINNT_VISTA                  0x0600 // Windows Vista
#define _WIN32_WINNT_WS08                   0x0600 // Windows Server 2008
#define _WIN32_WINNT_LONGHORN               0x0600 // Windows Vista
#define _WIN32_WINNT_WIN7                   0x0601 // Windows 7
#define _WIN32_WINNT_WIN8                   0x0602 // Windows 8
#define _WIN32_WINNT_WINBLUE                0x0603 // Windows 8.1
#define _WIN32_WINNT_WINTHRESHOLD           0x0A00 // Windows 10
#define _WIN32_WINNT_WIN10                  0x0A00 // Windows 10
```

Wenn nicht alle diese Windows-Versionen in der Kopie von SDKDDKVer.h angezeigt werden, die Sie sich ansehen, verwenden Sie wahrscheinlich eine ältere Version des Windows SDK. In der Standardeinstellung verwenden Win32-Projekte in Visual Studio 2017 das Windows 10 SDK.

> [!NOTE]
> Es ist nicht gewährleistet, dass die Werte auf jeden Fall funktionieren, wenn Sie interne MFC-Header in die Anwendung aufnehmen.

Dieses Makro kann auch mithilfe der `/D`-Compileroption definiert werden. Weitere Informationen finden Sie unter [/D (Preprocessor Definitions)](../build/reference/d-preprocessor-definitions.md).

Weitere Informationen zur Bedeutung dieser Makros finden Sie unter [Verwenden der Windows-Header](/windows/desktop/WinProg/using-the-windows-headers).

## <a name="see-also"></a>Siehe auch

[Änderungsverlauf von Visual C++](../porting/visual-cpp-change-history-2003-2015.md)
