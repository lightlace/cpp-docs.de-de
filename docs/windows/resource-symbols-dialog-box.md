---
title: Ressource Ressourcensymbol-Dialogfelds | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.editors.resourcesymbols
dev_langs:
- C++
helpviewer_keywords:
- New Symbol dialog box
- Resource Symbols dialog box
- Change Symbol dialog box
ms.assetid: 9706cde3-1f48-4fcd-bedb-2b03b455e3c1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0e21f60fb2ca90e9e4825e93103fa74be3563780
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="resource-symbols-dialog-box"></a>Ressourcensymbole (Dialogfeld)
Die **Ressourcensymbole** Dialogfeld können Sie neue Ressourcensymbole hinzufügen, ändern die Symbole, die angezeigt werden, oder fahren Sie mit der Position im Quellcode, in dem ein Symbol verwendet wird.  
  
 **Name**  
 Zeigt den Namen des Symbols an. Weitere Informationen finden Sie unter [Beschränkungen bei Symbolnamen](../windows/symbol-name-restrictions.md).  
  
 **Wert**  
 Zeigt den numerischen Wert des Symbols an. Weitere Informationen finden Sie unter [Beschränkungen für Symbolwerte](../windows/symbol-value-restrictions.md).  
  
 **In Verwendung**  
 Bei Auswahl dieser Option wird angegeben, dass das Symbol von einer oder mehreren Ressourcen verwendet wird. Die Ressourcen sind im Feld „Verwendet von aufgeführt“.  
  
 **Schreibgeschützte Symbole anzeigen**  
 Bei Auswahl dieser Option werden schreibgeschützte Ressourcen angezeigt. Standardmäßig werden im Dialogfeld „Ressourcensymbol“ nur die änderbaren Ressourcen in Ihrer Ressourcenskriptdatei angezeigt. Bei Auswahl dieser Option jedoch werden änderbare Ressourcen fett formatiert und schreibgeschützte Ressourcen in Nur-Text angezeigt.  
  
 **Verwendet von**  
 Zeigt die Ressource bzw. Ressourcen an, in der/denen das in der Symbolliste markierte Symbol verwendet wird. Um auf den Editor für eine bestimmte Ressource zu verschieben, wählen Sie die Ressource in der **verwendet von** Feld, und klicken Sie auf **Verwendung anzeigen**. Weitere Informationen finden Sie unter [Öffnen des Ressourcen-Editors für ein bestimmtes Symbol](../windows/opening-the-resource-editor-for-a-given-symbol.md).  
  
 **Neu**  
 Öffnet das Dialogfeld „Neues Symbol“, in dem Sie den Namen festlegen können und, falls erforderlich, einen Wert für einen neuen symbolischen Ressourcenbezeichner. Weitere Informationen finden Sie unter [Erstellen neuer Symbole](../windows/creating-new-symbols.md).  
  
 **Ändern**  
 Öffnet das Dialogfeld „Symbol ändern“, in dem Sie den Namen oder Wert eines Symbols ändern können. Wenn das Symbol für ein Steuerelement oder eine Ressource in Gebrauch ist, kann das Symbol nur im entsprechenden Ressourcen-Editor geändert werden. Weitere Informationen finden Sie unter [ändern nicht zugewiesener Symbole](../windows/changing-unassigned-symbols.md).  
  
 **Verwendung anzeigen**  
 Öffnet die Ressource, die das Symbol enthält, im entsprechenden Ressourcen-Editor. Weitere Informationen finden Sie unter [Öffnen des Ressourcen-Editors für ein bestimmtes Symbol](../windows/opening-the-resource-editor-for-a-given-symbol.md).  
  

  
## <a name="requirements"></a>Anforderungen  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Anzeigen von Ressourcensymbolen](../windows/viewing-resource-symbols.md)