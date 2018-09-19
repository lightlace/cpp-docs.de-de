---
title: 'Ressourcencompiler: Fehler RW2001 | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RW2001
dev_langs:
- C++
helpviewer_keywords:
- RW2001
ms.assetid: 963bdc7d-6ebe-4378-8bbc-47dfcf5d330c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f401ce7c9a96cfeecf195b8872a704b8b1291939
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46114981"
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