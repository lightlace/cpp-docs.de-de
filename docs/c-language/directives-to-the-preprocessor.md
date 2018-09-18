---
title: Anweisungen für den Präprozessor | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: adc6251e-cf6b-4508-bdbb-55f446c838d3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f1ddecf1e205cc9a6d7f09a27fbf243417540e49
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46033562"
---
# <a name="directives-to-the-preprocessor"></a>Anweisungen für den Präprozessor

„Anweisungen“ weisen den C-Präprozessor an, eine bestimmte Aktion für den Text des Programms vor der Kompilierung auszuführen. [Präprozessordirektiven](../preprocessor/preprocessor-directives.md) sind vollständig in *Präprozessorverweis* beschrieben. In diesem Beispiel wird die `#define`-Präprozessordirektive verwendet:

```
#define MAX 100
```

Diese Anweisung weist den Compiler an, vor der Kompilierung jedes Vorkommen von `MAX` durch `100` zu ersetzen. Die Präprozessordirektiven des C-Compilers sind:

|#define|#endif|#ifdef|#line|
|--------------|-------------|-------------|------------|
|`#elif`|`#error`|**#ifndef**|**#pragma**|
|`#else`|`#if`|`#include`|`#undef`|

## <a name="see-also"></a>Siehe auch

[Quelldateien und Quellprogramme](../c-language/source-files-and-source-programs.md)