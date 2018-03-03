---
title: "Vorgehensweise: Ändern von Sprache oder Bedingung einer Ressource während des Kopiervorgangs | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.resvw.resource.changing
dev_langs:
- C++
helpviewer_keywords:
- Language property
- condition property of resource
ms.assetid: 8f622ab0-bac2-468f-ae70-78911afc4759
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3655366e8851494482e628b9c260c796df3f64bd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-change-the-language-or-condition-of-a-resource-while-copying"></a>Gewusst wie: Ändern der Sprache oder Bedingung einer Ressource während des Kopierens
Beim Kopieren in eine Ressource können Sie ihre Sprachen- und/oder Bedingungseigenschaft ändern.  
  
-   Die Ressourcensprache ermittelt lediglich die Sprache für die Ressource. Dies dient der [FindResource](http://msdn.microsoft.com/library/windows/desktop/ms648042) um die Ressource zu bestimmen, für die Sie suchen. (Ressourcen können für jede Sprache Unterschiede aufweisen, die nicht mit dem Text zusammenhängen, z. B. Tastenkombinationen, die nur auf einer japanischen Tastatur funktionieren, oder eine Bitmap, die nur für Builds in Chinesisch gilt usw.)  
  
-   Die Bedingung einer Ressource stellt ein definiertes Symbol dar, das eine Bedingung angibt, unter der diese bestimmte Ressourcenkopie zu verwenden ist.  
  
 Sprache und Bedingung einer Ressource werden im Arbeitsbereichsfenster nach dem Ressourcennamen in Klammern angezeigt. In diesem Beispiel verwendet die Ressource mit dem Namen „IDD_AboutBox“ Finnisch als Sprache und „XX33“ als Bedingung.  
  
```  
IDD_AboutBox (Finnish - XX33)  
```  
  
### <a name="to-copy-an-existing-resource-and-change-its-language-or-condition"></a>So kopieren Sie eine vorhandene Ressource und ändern die Sprache oder Bedingung  
  
1.  In der RC-Datei oder in der [Ressourcenansicht](../windows/resource-view-window.md) Fenster mit der rechten Maustaste der Ressource, die Sie kopieren möchten.  
  
2.  Wählen Sie **Kopie einfügen** aus dem Kontextmenü.  
  
3.  In der **Ressourcenkopie** (Dialogfeld):  
  
    -   Für die **Sprache** Listenfeld, wählen Sie die Sprache.  
  
    -   In der **Bedingung** geben die Bedingung.  
  

  
 Anforderungen  
  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Kopieren von Ressourcen](../windows/how-to-copy-resources.md)   
 [Ressourcendateien](../windows/resource-files-visual-studio.md)   
 [Ressourcen-Editor](../windows/resource-editors.md)