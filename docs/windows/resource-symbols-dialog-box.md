---
title: "Dialogfeld &quot;Ressourcensymbole&quot;"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.editors.resourcesymbols"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Neues Symbol (Dialogfeld)"
  - "Ressourcensymbole (Dialogfeld)"
  - "Symbol ändern (Dialogfeld)"
ms.assetid: 9706cde3-1f48-4fcd-bedb-2b03b455e3c1
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Dialogfeld &quot;Ressourcensymbole&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Im Dialogfeld **Ressourcensymbole** können Sie neue Ressourcensymbole hinzufügen, angezeigte Symbole ändern oder Stellen im Quellcode überspringen, an denen ein Symbol verwendet wird.  
  
 **Name**  
 Zeigt den Namen des Symbols an.  Weitere Informationen finden Sie unter [Beschränkungen bei Symbolnamen](../windows/symbol-name-restrictions.md).  
  
 **Wert**  
 Zeigt den numerischen Wert des Symbols an.  Weitere Informationen finden Sie unter [Beschränkungen bei Symbolwerten](../windows/symbol-value-restrictions.md).  
  
 **In Verwendung**  
 Bei Auswahl dieser Option wird angegeben, dass das Symbol von einer oder mehreren Ressourcen verwendet wird.  Die Ressourcen sind im Feld „Verwendet von aufgeführt“.  
  
 **Schreibgeschützte Symbole anzeigen**  
 Bei Auswahl dieser Option werden schreibgeschützte Ressourcen angezeigt.  Standardmäßig werden im Dialogfeld „Ressourcensymbol“ nur die änderbaren Ressourcen in Ihrer Ressourcenskriptdatei angezeigt. Bei Auswahl dieser Option jedoch werden änderbare Ressourcen fett formatiert und schreibgeschützte Ressourcen in Nur\-Text angezeigt.  
  
 **Verwendet von**  
 Zeigt die Ressource bzw. Ressourcen an, in der\/denen das in der Symbolliste markierte Symbol verwendet wird.  Um zum Editor für eine bestimmte Ressource zu wechseln, wählen Sie die Ressource im Feld **Verwendet von** aus, und klicken Sie auf **Verwendung anzeigen**.  Weitere Informationen finden Sie unter [Öffnen des Ressourcen\-Editors für ein bestimmtes Symbol](../windows/opening-the-resource-editor-for-a-given-symbol.md).  
  
 **Neu**  
 Öffnet das Dialogfeld „Neues Symbol“, in dem Sie den Namen festlegen können und, falls erforderlich, einen Wert für einen neuen symbolischen Ressourcenbezeichner.  Weitere Informationen finden Sie unter [Erstellen neuer Symbole](../windows/creating-new-symbols.md).  
  
 **Änderung**  
 Öffnet das Dialogfeld „Symbol ändern“, in dem Sie den Namen oder Wert eines Symbols ändern können.  Wenn das Symbol für ein Steuerelement oder eine Ressource in Gebrauch ist, kann das Symbol nur im entsprechenden Ressourcen\-Editor geändert werden.  Weitere Informationen finden Sie unter [Ändern nicht zugewiesener Symbole](../windows/changing-unassigned-symbols.md).  
  
 **Verwendung anzeigen**  
 Öffnet die Ressource, die das Symbol enthält, im entsprechenden Ressourcen\-Editor.  Weitere Informationen finden Sie unter [Öffnen des Ressourcen\-Editors für ein bestimmtes Symbol](../windows/opening-the-resource-editor-for-a-given-symbol.md).  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Anforderungen  
 Win32  
  
## Siehe auch  
 [Viewing Resource Symbols](../windows/viewing-resource-symbols.md)