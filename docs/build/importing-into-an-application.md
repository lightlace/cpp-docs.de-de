---
title: Importieren in eine Anwendung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DLLs [C++], importing
- importing DLLs [C++], applications
- applications [C++], importing into
ms.assetid: 9d646466-e12e-4710-8ad9-c819c0375fcc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e88d34ce685e22e561683cc33db25997650ed7fd
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45718383"
---
# <a name="importing-into-an-application"></a>Importieren in eine Anwendung

Sie können Funktionen in einer Anwendung mit zwei Methoden importieren:

- Verwenden Sie die Schlüsselwörter **von "__declspec(dllimport)" "** in einer Funktionsdefinition in der hauptanwendung

- Verwenden Sie eine Moduldefinitionsdatei (.def) zusammen mit **von "__declspec(dllimport)" "**

## <a name="what-do-you-want-to-do"></a>Wie möchten Sie vorgehen?

- [Importieren in eine Anwendung mithilfe von "__declspec(dllimport)" "](../build/importing-into-an-application-using-declspec-dllimport.md)

- [Importieren von Funktionsaufrufen mithilfe von "__declspec(dllimport)" "](../build/importing-function-calls-using-declspec-dllimport.md)

- [Importieren von Daten mithilfe von "__declspec(dllimport)" "](../build/importing-data-using-declspec-dllimport.md)

- [Importieren Sie mithilfe von DEF-Dateien](../build/importing-using-def-files.md)

## <a name="see-also"></a>Siehe auch

[Importieren und Exportieren](../build/importing-and-exporting.md)