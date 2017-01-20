---
title: "Hinzuf&#252;gen einer lokalen Eigenschaft (Visual C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Schnittstellen, Hinzufügen von Eigenschaften"
  - "Eigenschaften [C++], Hinzufügen zu Schnittstellen"
ms.assetid: 37bd4db7-efd3-4faa-87ad-64902ed16a36
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Hinzuf&#252;gen einer lokalen Eigenschaft (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Mithilfe des [Assistenten zum Hinzufügen von Eigenschaften](../ide/names-add-property-wizard.md) können Sie einer Schnittstelle im Projekt eine Eigenschaft hinzufügen.  
  
### So fügen Sie einem Objekt eine Eigenschaft hinzu  
  
1.  Klicken Sie in der [Klassenansicht](assetId:///8d7430a9-3e33-454c-a9e1-a85e3d2db925) mit der rechten Maustaste auf den Namen der Schnittstelle, der die Eigenschaft hinzugefügt werden soll.  
  
    > [!NOTE]
    >  Sie können Eigenschaften auch Dispatchschnittstellen hinzufügen, die innerhalb des Bibliotheksknotens geschachtelt sind, sofern das Projekt nicht attributiert ist.  
  
2.  Klicken Sie im Kontextmenü auf **Hinzufügen** und dann auf **Eigenschaft hinzufügen**.  
  
3.  Geben Sie im [Assistenten zum Hinzufügen von Eigenschaften](../ide/names-add-property-wizard.md) die Information zum Erstellen der Eigenschaft ein.  
  
4.  Nehmen Sie auf der Assistentenseite [IDL\-Attribute](../ide/idl-attributes-add-property-wizard.md) die Einstellungen zur IDL \(Interface Definition Language\) für diese Eigenschaft vor.  
  
5.  Klicken Sie auf **Fertig stellen**, um die Eigenschaft hinzuzufügen.  
  
 Die zur Eigenschaft gehörigen Methoden **Get** und `Put` werden in der Klassenansicht unter der Schnittstelle, für die die Eigenschaft definiert wird, anhand von zwei Symbolen dargestellt.  Sie können auf eines der Symbole doppelklicken, um die jeweilige Eigenschaftsdeklaration in der IDL\-Datei anzuzeigen.  
  
-   Bei ATL\-Schnittstellen werden die Funktionen **Get** und **Put** der CPP\-Datei hinzugefügt. Außerdem werden der H\-Datei Verweise auf diese Funktionen hinzugefügt.  
  
-   Wenn Sie für MFC\-Dispatchschnittstellen **Membervariable** als Implementierungstyp auswählen, wird der Klasse, durch die die Implementierung erfolgt, eine Methode und eine Variable hinzugefügt.  Wenn Sie als Implementierungstyp **Get\/Set\-Methoden** auswählen, werden der Klasse, durch die die Implementierung erfolgt, zwei Methoden hinzugefügt.  
  
## Siehe auch  
 [Erstellen einer COM\-Schnittstelle](../ide/creating-a-com-interface-visual-cpp.md)   
 [Bearbeiten einer COM\-Schnittstelle](../ide/editing-a-com-interface.md)   
 [Das Komponentenobjektmodell](http://msdn.microsoft.com/library/windows/desktop/ms694363)   
 [Schnittstellenzeiger und Schnittstellen](http://msdn.microsoft.com/library/windows/desktop/ms688484)