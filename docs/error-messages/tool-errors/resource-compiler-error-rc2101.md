---
title: 'Ressourcencompiler: Fehler RC2101'
ms.date: 11/04/2016
f1_keywords:
- RC2101
helpviewer_keywords:
- RC2101
ms.assetid: 580f9d74-162f-41e9-9438-ddbe3457c359
ms.openlocfilehash: 595e87b73d79a01993e0e9b3aaa814332b21413f
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345279"
---
# <a name="resource-compiler-error-rc2101"></a>Ressourcencompiler: Fehler RC2101

Ungültige Richtlinie im vorverarbeiteten RC-Datei

Die Ressourcencompiler-Datei enthält eine **#pragma** Richtlinie.

Verwenden der **#ifndef** Präprozessordirektive der RC_INVOKED-Konstante, dass der Ressourcencompiler definiert, bei der Verarbeitung einer Include-Datei. Ort der **#pragma** -Direktive innerhalb eines Blocks von Code, die nicht verarbeitet wird, wenn die Invoked-Konstante definiert ist. Code im Block wird nur von C/C++-Compiler und nicht von der Ressourcencompiler verarbeitet. Im folgenden Beispielcode wird diese Technik veranschaulicht:

```
#ifndef RC_INVOKED
#pragma pack(2)  // C/C++ only, ignored by Resource Compiler
#endif
```

Die **#pragma** Präprozessordirektive hat keine Bedeutung ein. RC-Datei. Die **#include** Präprozessordirektive werden häufig in ein. RC-Datei, die eine Headerdatei (eine Projekt-basierten benutzerdefinierten Header-Datei oder ein Standardheader-Datei, die mit einem seiner Produkte von Microsoft bereitgestellten) enthalten. Einige dieser include-Dateien enthalten die **#pragma** Richtlinie. Da eine Headerdatei eine oder mehrere andere Headerdateien, die Datei enthalten kann, die die auslösende enthält **#pragma** Richtlinie möglicherweise nicht sofort ersichtlich.

Die **#ifndef** RC_INVOKED Technik kann steuern, einschließlich Headerdateien in projektbasierten Headerdateien.