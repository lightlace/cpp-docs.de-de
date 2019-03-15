---
title: Importieren von Daten mithilfe von "__declspec(dllimport)"
ms.date: 11/04/2016
f1_keywords:
- dllimport
helpviewer_keywords:
- importing data [C++]
- dllimport attribute [C++], data imports
- __declspec(dllimport) keyword [C++]
- importing DLLs [C++], __declspec(dllimport)
ms.assetid: 0ae70b39-87c7-4181-8be9-e786e0db60b0
ms.openlocfilehash: 74ad93e640a4e961f7670077227bb5c35a42c20f
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57818426"
---
# <a name="importing-data-using-declspecdllimport"></a>Importieren von Daten mithilfe von "__declspec(dllimport)"

Im Fall von Daten mithilfe von **von "__declspec(dllimport)" "** bietet eine bequeme Möglichkeit, die eine Schicht der Dereferenzierung entfernt. Beim Importieren von Daten aus einer DLL müssen Sie weiterhin die Importadresstabelle durchlaufen. Vor dem **von "__declspec(dllimport)" "**, dies bedeutete, mussten Sie denken Sie daran, führen eine zusätzliche Dereferenzierungsebene aus, wenn Sie den Zugriff auf Daten, die von der DLL exportiert:

```
// project.h
#ifdef _DLL   // If accessing the data from inside the DLL
   ULONG ulDataInDll;

#else         // If accessing the data from outside the DLL
   ULONG *ulDataInDll;
#endif
```

Sie würden dann exportieren, die Daten in Ihrer. DEF-Datei:

```
// project.def
LIBRARY project
EXPORTS
   ulDataInDll   CONSTANT
```

und ihn außerhalb der DLL zugreifen:

```
if (*ulDataInDll == 0L)
{
   // Do stuff here
}
```

Wenn Sie die Daten als markieren **von "__declspec(dllimport)" "**, generiert der Compiler die Dereferenzierung Code automatisch für Sie. Sie müssen nicht mehr über die oben genannten Schritte machen. Wie bereits erwähnt, verwenden Sie keine **von "__declspec(dllimport)" "** Deklaration für die Daten beim Erstellen der DLL. Funktionen in der DLL verwenden nicht die Importadresstabelle das Datenobjekt, das Zugriff auf. aus diesem Grund müssen Sie nicht die zusätzliche Ebene der Dereferenzierung vorhanden.

Um die Daten automatisch aus der DLL zu exportieren, verwenden Sie diese Deklaration:

```
__declspec(dllexport) ULONG ulDataInDLL;
```

## <a name="see-also"></a>Siehe auch

[Importieren in eine Anwendung](importing-into-an-application.md)
