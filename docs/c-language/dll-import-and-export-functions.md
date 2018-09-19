---
title: Import- und Exportfunktionen einer DLL | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- DLLs [C++], importing
- dllimport attribute [C++], storage-class attribute
- DLL exports [C++]
- declaring functions, with dllexport and dllimport
- extended storage-class attributes
- dllexport attribute [C++], storage-class attribute
ms.assetid: 08d164b9-770a-4e14-afeb-c6f21d9e33e4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3da47c4d6c5af518660b5799b3bf9ae3f512a6fe
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46029220"
---
# <a name="dll-import-and-export-functions"></a>Import- und Exportfunktionen einer DLL

**Microsoft-spezifisch**

Die vollständigsten und aktuellsten Informationen zu diesem Thema finden Sie unter [dllexport, dllimport](../cpp/dllexport-dllimport.md).

Die Speicherklassenmodifizierer **dllimport** und `dllexport` sind Microsoft-spezifische Erweiterungen der Sprache C. Diese Modifizierer definieren explizit die Schnittstelle der DLL mit dem Client (die ausführbare Datei oder eine andere DLL). Durch das Deklarieren von Funktionen als `dllexport` ist keine Moduldefinitionsdatei (.DEF) notwendig. Sie können auch die **dllimport**- und `dllexport`-Modifizierer mit Daten und Objekten verwenden.

Die **dllimport** und `dllexport`-Speicherklassenmodifizierer müssen mit dem erweiterten Schlüsselwort der Attributsyntax, `__declspec`, wie in diesem Beispiel gezeigt verwendet werden:

```
#define DllImport   __declspec( dllimport )
#define DllExport   __declspec( dllexport )

DllExport void func();
DllExport int i = 10;
DllExport int j;
DllExport int n;
```

Spezifische Informationen zur Syntax für erweiterte Speicherklassenmodifizierer finden Sie unter [Erweiterte Speicherklassenattribute](../c-language/c-extended-storage-class-attributes.md).

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[C-Funktionsdefinitionen](../c-language/c-function-definitions.md)