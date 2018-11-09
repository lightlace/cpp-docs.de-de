---
title: Anweisungen für den Präprozessor
ms.date: 11/04/2016
ms.assetid: adc6251e-cf6b-4508-bdbb-55f446c838d3
ms.openlocfilehash: 0abc21f38f5776acd9167f0526160dc5e1bb8cbb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50450053"
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