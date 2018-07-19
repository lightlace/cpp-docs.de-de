---
title: Compilerwarnung (Stufe 1) C4655 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4655
dev_langs:
- C++
helpviewer_keywords:
- C4655
ms.assetid: 540f2c7a-e4a1-49af-84b4-03eeea1bbf41
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6011bf3a2a3bf1718fc15823f2541f49306857c8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33283262"
---
# <a name="compiler-warning-level-1-c4655"></a>Compilerwarnung (Stufe 1) C4655
**'**   
 ***Symbol* ': Variablentyp ist seit dem letzten Build neu, oder an anderer Stelle unterschiedlich definiert ist**  
  
 Seit dem letzten erfolgreichen Build wurde ein Datentyp geändert oder hinzugefügt. „Bearbeiten und fortfahren“ unterstützt keine Änderungen an vorhandenen Datentypen.  
  
 Auf diese Warnung folgt ein [Schwerwiegender Fehler C1092](../../error-messages/compiler-errors-1/fatal-error-c1092.md). Weitere Informationen hierzu finden Sie unter [Unterstützte Codeänderungen](/visualstudio/debugger/supported-code-changes-cpp).  
  
### <a name="to-remove-this-warning-without-ending-the-current-debug-session"></a>So entfernen Sie diese Warnung, ohne die aktuelle Debugsitzung zu beenden  
  
1.  Ändern Sie den Datentyp wieder in den Zustand, den er vor dem Fehler hatte.  
  
2.  Wählen Sie im Menü **Debuggen** den Befehl **Codeänderungen übernehmen**.  
  
### <a name="to-remove-this-warning-without-changing-your-source-code"></a>So entfernen Sie diese Warnung, ohne den Quellcode zu ändern  
  
1.  Wählen Sie im Menü **Debuggen** die Option **Debuggen beenden**.  
  
2.  Wählen Sie im Menü **Erstellen** den Befehl **Erstellen**aus.