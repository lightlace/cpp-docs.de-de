---
title: 'Symbole: Ressourcenbezeichner | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.editors.symbol.identifiers
dev_langs: C++
helpviewer_keywords:
- symbols, resource identifiers
- symbols, creating
- resource symbols
- symbols, editing
- resource editors, resource symbols
ms.assetid: 8fccc09a-0237-4a65-b9c4-57d60c59e324
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7b47af70aa2f9bd4bb8b4ea7a5a9b8591164b5e8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="symbols-resource-identifiers"></a>Symbole: Ressourcenbezeichner
Ein Symbol ist ein Ressourcenbezeichner (ID), der aus zwei Teilen besteht: einer Textzeichenfolge (Symbolname), die einem ganzzahligen Wert (Symbolwert) zugeordnet ist. Zum Beispiel:  
  
```  
IDC_EDITNAME = 5100  
```  
  
 Symbolnamen werden meistens als Bezeichner bezeichnet.  
  
 Symbole bieten eine anschauliche Möglichkeit, auf Ressourcen und Objekte der Benutzeroberfläche zu verweisen, sowohl im Quellcode als auch bei der Arbeit im Ressourcen-Editor. Mithilfe des Dialogfelds [Ressourcensymbole](../windows/viewing-resource-symbols.md)können Symbole komfortabel an einem Ort angezeigt und bearbeitet werden.  
  
 Wenn Sie eine neue Ressource oder ein neues Ressourcenobjekt erstellen, stellt der [Ressourcen-Editor](../windows/resource-editors.md) einen Standardnamen für die Ressource bereit, z. B. `IDC_RADIO1`, und weist ihr einen Wert zu. Die Name-plus-Wert-Definition wird in der Datei „Resource.h“ gespeichert.  
  
> [!NOTE]
>  Wenn Sie Ressourcen oder Ressourcenobjekte aus einer RC-Datei in eine andere kopieren, ändert Visual C++ möglicherweise den Symbolwert der übertragenen Ressource, oder den Symbolnamen und den Wert, um Konflikte mit Symbolnamen oder Werten in der vorhandenen Datei zu vermeiden.  
  
 In dem Maß, in dem Ihre Anwendung in Umfang und Komplexität wächst, wächst auch die Anzahl ihrer Ressourcen und Symbole. Das Nachverfolgen einer großen Zahl von Symbolen, die über verschiedene Dateien verteilt sind, kann schwierig sein. Das Dialogfeld [Ressourcensymbole](../windows/resource-symbols-dialog-box.md) vereinfacht die Symbolverwaltung, indem es ein zentrales Tool bereitstellt, das Ihnen folgende Möglichkeiten bietet:  
  
- [Anzeigen von Ressourcensymbolen](../windows/viewing-resource-symbols.md)  
  
- [Erstellen neuer Symbole](../windows/creating-new-symbols.md)  
  
- [Ändern nicht zugewiesener Symbole](../windows/changing-unassigned-symbols.md)  
  
- [Löschen nicht zugewiesener Symbole](../windows/deleting-unassigned-symbols.md)  
  
- [Öffnen des Ressourcen-Editors für ein bestimmtes Symbol](../windows/opening-the-resource-editor-for-a-given-symbol.md)  
  
- [Ändern eines Symbols oder Symbolnamens (ID)](../windows/changing-a-symbol-or-symbol-name-id.md)  
  
- [Ändern des numerischen Werts eines Symbols](../windows/changing-a-symbol-s-numeric-value.md)  
  
- [Ändern der Namen von Symbolheaderdateien](../windows/changing-the-names-of-symbol-header-files.md)  
  
- [Einschließen gemeinsam genutzter (schreibgeschützter) oder berechneter Symbole](../windows/including-shared-read-only-or-calculated-symbols.md)  
  
- [Anzeigen vordefinierter Symbol-IDs](../windows/predefined-symbol-ids.md)  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](https://msdn.microsoft.com/library/f45fce5x.aspx) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](https://msdn.microsoft.com/library/xbx3z216.aspx). Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing und Lokalisieren von .NET Framework-Anwendungen](https://msdn.microsoft.com/library/h6270d0z.aspx).  
  
## <a name="requirements"></a>Anforderungen  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Symbolsuche in Ressourcen](../windows/how-to-search-for-symbols-in-resources.md)   
 [Ressourcen-Editoren](../windows/resource-editors.md)   
 [Ressourcendateien](../windows/resource-files-visual-studio.md)

