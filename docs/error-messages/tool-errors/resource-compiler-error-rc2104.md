---
title: 'Ressourcencompiler: Fehler RC2104 | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- RC2104
dev_langs:
- C++
helpviewer_keywords:
- RC2104
ms.assetid: 792a3bd8-cb4c-4817-b288-4ce37082b582
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ce7fa189e03ec907c4b42f381096f095d5df734a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-error-rc2104"></a>Ressourcencompiler: Fehler RC2104
Undefiniertes Schlüsselwort oder Schlüsselname: Schlüssel  
  
 Das angegebene Schlüsselwort oder der Schlüsselname ist nicht definiert.  
  
 Dieser Fehler wird häufig durch einen Tippfehler in die Definition der Ressource oder in der zugehörigen Header-Datei verursacht. Er kann auch durch eine fehlende Headerdatei verursacht werden.  
  
 Um das Problem zu beheben, suchen Sie die Header-Datei, die das definierte Schlüsselwort oder den Schlüsselnamen enthält und stellen Sie sicher, dass er in Ihrer Ressourcendatei enthalten ist und dass das Schlüsselwort oder der Schlüsselname richtig geschrieben ist. Wenn das Projekt mit einem vorkompilierten Header erstellt wurde und Sie es anschließend entfernen, stellen Sie sicher, dass die Ressourcendatei erforderliche Header enthält.  
  
 So überprüfen die definierten Schlüsselwörter und Schlüsselnamen in Ihrer Ressourcendatei in Visual Studio, öffnen Sie die **Ressourcenansicht** Fenster – Wählen Sie in der Menüleiste **Ansicht**, **Ressourcenansicht**– und Klicken Sie dann das Kontextmenü für die RC-Datei öffnen, und wählen Sie **Ressourcensymbole** um die Liste der definierten Symbole anzuzeigen. Um die enthaltenen Header zu ändern, öffnen Sie das Kontextmenü für die RC-Datei, und wählen Sie **Ressourcenincludes**.  
  
 Wenn Sie diese Meldung erhalten:  
  
```  
undefined keyword or key name: MFT_STRING   
```  
  
 Öffnen Sie \MCL\MFC\Include\AfxRes.h, und fügen Sie diese Eingüge-Direktive ein:  
  
```  
#include <winresrc.h>  
```