---
title: Schwerwiegender Fehler C1010 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1010
dev_langs:
- C++
helpviewer_keywords:
- C1010
ms.assetid: dfd035f1-a7a2-40bc-bc92-dc4d7f456767
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bf8af35b28cfa02bd2723ff3c78db04a27cc39ba
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33198494"
---
# <a name="fatal-error-c1010"></a>Schwerwiegender Fehler C1010
Unerwartetes Dateiende während der Suche nach dem vorkompilierten Header. Haben Sie vergessen hinzufügen ' #include ", im Quellcode?  
  
 Eine Includedatei mit angegebenen ["/ Yu"](../../build/reference/yu-use-precompiled-header-file.md) ist nicht in der Quelldatei aufgeführt.  Diese Option ist standardmäßig aktiviert, in den meisten Visual C++-Projekttypen, und "stdafx.h" ist die Standardeinstellung include-Datei, die durch diese Option angegeben.  
  
 Verwenden Sie in der Visual Studio-Umgebung eine der folgenden Methoden zum Beheben dieses Fehlers:  
  
-   Wenn Sie in Ihrem Projekt vorkompilierte Header nicht verwenden, legen Sie die **vorkompilierten Header erstellen/verwenden** Eigenschaft Quelldateien **vorkompilierte Header nicht verwenden**. Zum Festlegen dieser Compileroption, gehen Sie folgendermaßen vor:  
  
    1.  Wählen Sie im Bereich "Projektmappen-Explorer" des Projekts mit der rechten Maustaste des Projektnamens, und klicken Sie dann auf **Eigenschaften**.  
  
    2.  Klicken Sie im linken Bereich auf die **C/C++-** Ordner.  
  
    3.  Klicken Sie auf die **vorkompilierte Header** Knoten.  
  
    4.  Klicken Sie im rechten Bereich auf **vorkompilierten Header erstellen/verwenden**, und klicken Sie dann auf **vorkompilierte Header nicht verwenden**.  
  
-   Stellen Sie sicher, dass Sie nicht versehentlich gelöscht, umbenannt oder entfernt Headerdatei (standardmäßig "stdafx.h") aus dem aktuellen Projekt. Diese Datei muss vor jedem anderen Code in den Quellcodedateien mit einzuschließenden **#include "stdafx.h"**. (Diese Headerdatei wird angegeben, als **PCH durch Datei erstellen/verwenden** Projekteigenschaft)