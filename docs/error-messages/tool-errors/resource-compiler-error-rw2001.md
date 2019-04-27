---
title: 'Ressourcencompiler: Fehler RW2001'
ms.date: 11/04/2016
f1_keywords:
- RW2001
helpviewer_keywords:
- RW2001
ms.assetid: 963bdc7d-6ebe-4378-8bbc-47dfcf5d330c
ms.openlocfilehash: 4d298cdd9d96c55f283ce7f0e2ba04dd664941f8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62226504"
---
# <a name="resource-compiler-error-rw2001"></a>Ressourcencompiler: Fehler RW2001

Ungültige Richtlinie im vorverarbeiteten RC-Datei

Die RC-Datei enthält eine **#pragma** Richtlinie.

Verwenden der **#ifndef** Präprozessordirektive der **RC_INVOKED** Konstanten, dass der Ressourcencompiler definiert, bei der Verarbeitung einer Include-Datei. Ort der **#pragma** -Direktive innerhalb eines Codeblocks, der nicht verarbeitet, wenn die **RC_INVOKED** Konstante definiert ist. Code im Block wird nur von C/C++-Compiler und nicht von der Ressourcencompiler verarbeitet. Im folgenden Beispielcode wird diese Technik veranschaulicht:

```
#ifndef RC_INVOKED
#pragma pack(2)  // C/C++ only, ignored by Resource Compiler
#endif
```

Die **#pragma** Präprozessordirektive hat keine Bedeutung ein. RC-Datei. Die **#include** Präprozessordirektive werden häufig in ein. RC-Datei, die eine Headerdatei (eine Projekt-basierten benutzerdefinierten Header-Datei oder ein Standardheader-Datei, die mit einem seiner Produkte von Microsoft bereitgestellten) enthalten. Einige dieser include-Dateien enthalten die **#pragma** Richtlinie. Da eine Headerdatei eine oder mehrere andere Headerdateien, die Datei enthalten kann, die die auslösende enthält **#pragma** Richtlinie möglicherweise nicht sofort ersichtlich.

Die **#ifndef RC_INVOKED** Technik kann steuern, einschließlich Headerdateien in projektbasierten Headerdateien.