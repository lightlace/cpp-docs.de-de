---
title: 'Ressourcencompiler: Fehler RC2101 | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC2101
dev_langs:
- C++
helpviewer_keywords:
- RC2101
ms.assetid: 580f9d74-162f-41e9-9438-ddbe3457c359
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 196806e6d2767c889ae96d239af69113c542ba6c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46034758"
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