---
title: "Eigenschaft &quot;Typ&quot; von Zugriffstasten | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Type-Eigenschaft"
  - "VIRTKEY"
ms.assetid: 8c349bc4-e6ad-43fa-959e-f29168af35b8
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Eigenschaft &quot;Typ&quot; von Zugriffstasten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Durch die **Typ**\-Eigenschaft einer Zugriffstaste wird bestimmt, ob die mit der Zugriffstasten\-ID verknüpfte Tastenkombination eine virtuelle Tastenkombination oder ein ASCII\/ANSI\-Tastenwert ist:  
  
-   Hat die **Typ**\-Eigenschaft den Wert **ASCII**, darf der [Modifizierer](../windows/accelerator-modifier-property.md) nur None oder Alt lauten; ansonsten kann ihm eine Zugriffstaste zugeordnet werden, in der die STRG\-TASTE verwendet wird \(in diesem Fall ist der Taste das Zirkumflexzeichen \(^\) vorangestellt\).  
  
-   Wenn die **Typ**\-Eigenschaft den Wert **VIRTKEY** aufweist, können Modifizierer\- und Tastenwerte beliebig kombiniert werden.  
  
    > [!NOTE]
    >  Wenn Sie einen Wert in die Zugriffstastentabelle eingeben möchten, der als ASCII\/ANSI\-Wert behandelt werden soll, klicken Sie für den Tabelleneintrag einfach auf den entsprechenden Typ, und wählen Sie ASCII aus der Dropdownliste aus.  Wenn Sie die Taste jedoch mit dem Befehl **Nächste Taste** \(Menü **Bearbeiten**\) festlegen, müssen Sie *vor* der Eingabe des Tastencodes die **Typ**\-Eigenschaft von VIRTKEY in ASCII ändern.  
  
## Anforderungen  
 Win32  
  
## Siehe auch  
 [Setting Accelerator Properties](../windows/setting-accelerator-properties.md)   
 [Accelerator Editor](../mfc/accelerator-editor.md)