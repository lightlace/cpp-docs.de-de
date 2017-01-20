---
title: "Gewusst wie: Erstellen einer Meldungszuordnung f&#252;r eine Vorlagenklasse"
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
  - "Meldungszuordnungen, Vorlagenklassen"
  - "Vorlagenklassen, Erstellen von Meldungszuordnungstabellen"
ms.assetid: 4e7e24f8-06df-4b46-82aa-7435c8650de3
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Erstellen einer Meldungszuordnung f&#252;r eine Vorlagenklasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Meldungszuordnung in MFC bietet eine effiziente Möglichkeit, Windows\-Meldungen auf eine entsprechende C\+\+\-Objektinstanz zu verweisen.  Beispiele für MFC\-Meldungszuordnungszielen enthalten Anwendungsklassen, Dokument und Ansichtsklassen, Steuerelementklassen, u. a.  
  
 Herkömmliche MFC\-Meldungszuordnungen werden mithilfe des Makros [BEGIN\_MESSAGE\_MAP](../Topic/BEGIN_MESSAGE_MAP.md) deklariert, um den Anfang der Meldungszuordnung, einen Makroeintrag für jede Meldungshandlerklassenmethode, und das [END\_MESSAGE\_MAP](../Topic/END_MESSAGE_MAP.md)\-Makro deklarieren, das Ende der Meldungszuordnung schließlich zu deklarieren.  
  
 Eine Einschränkung mit dem Makro [BEGIN\_MESSAGE\_MAP](../Topic/BEGIN_MESSAGE_MAP.md) tritt auf, wenn sie in Verbindung mit einer Klasse verwendet wird, müssen die Vorlagenargumente enthält.  Wenn es einer Vorlagenklasse verwendet wird, führt dieses Makro einen Kompilierungsfehler aufgrund von fehlenden Vorlagenparameter während der Erweiterung.  Das Makro [BEGIN\_TEMPLATE\_MESSAGE\_MAP](../Topic/BEGIN_TEMPLATE_MESSAGE_MAP.md) wurde entworfen, um die Klassen zu erstellen, die ein einzelnes Vorlagenargument enthalten, eigene Meldungszuordnungen zu deklarieren.  
  
## Beispiel  
 Betrachten Sie ein Beispiel, in dem die Klasse MFC\- [CListBox](../mfc/reference/clistbox-class.md) erweitert wird, um die Synchronisierung mit einer externen Datenquelle bereitgestellt.  Die fiktive **CSyncListBox**\-Klasse deklariert ist, wie folgt:  
  
 [!CODE [NVC_MFC_CListBox#42](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_CListBox#42)]  
  
 Die **CSyncListBox**\-Klasse basiert auf einem einzelnen Typ vorlagenbasiert, der die Datenquelle, die beschreibt, sie mit synchronisiert.  Es deklariert auch drei Methoden, die in der Meldungszuordnung der Klasse einbezogen werden: **OnPaint**, **OnDestroy** und **OnSynchronize**.  Die **OnSynchronize**\-Methode wird implementiert, wie folgt:  
  
 [!CODE [NVC_MFC_CListBox#43](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_CListBox#43)]  
  
 Die obige Implementierung können die in einem Klassentyp, der die **GetCount**\-Methode, wie **CArray**, **CList** implementiert, und **CMap** spezialisiert werden **CSyncListBox**\-Klasse.  Die **StringizeElement**\-Funktion ist eine Vorlagenfunktion, die durch Folgendes einen Prototyp entwickelt wird:  
  
 [!CODE [NVC_MFC_CListBox#44](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_CListBox#44)]  
  
 Normalerweise würde die Meldungszuordnung für diese Klasse folgendermaßen definiert:  
  
 `BEGIN_MESSAGE_MAP(CSyncListBox, CListBox)`  
  
 `ON_WM_PAINT()`  
  
 `ON_WM_DESTROY()`  
  
 `ON_MESSAGE(LBN_SYNCHRONIZE, OnSynchronize)`  
  
 `END_MESSAGE_MAP()`  
  
 bei **LBN\_SYNCHRONIZE** eine benutzerdefinierte Benutzermeldung ist, die von der Anwendung definiert ist, z:  
  
 [!CODE [NVC_MFC_CListBox#45](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_CListBox#45)]  
  
 Die oben aufgeführten Makrozuordnung kompiliert, nicht aufgrund der Tatsache, den die Vorlagenspezifikation für die **CSyncListBox**\-Klasse während der Makroerweiterung fehlen wird.  Das Makro **BEGIN\_TEMPLATE\_MESSAGE\_MAP** löst dies, indem den angegebenen Vorlagenparameter in die erweiterte Makrozuordnung integriert.  Die Meldungszuordnung für diese Klasse wird:  
  
 [!CODE [NVC_MFC_CListBox#46](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_CListBox#46)]  
  
 Im Folgenden wird veranschaulicht Beispielverwendung der **CSyncListBox**\-Klasse mithilfe eines **CStringList**\-Objekts:  
  
 [!CODE [NVC_MFC_CListBox#47](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_CListBox#47)]  
  
 Um den Test abzuschließen, muss die **StringizeElement**\-Funktion spezialisiert werden mit der **CStringList**\-Klasse funktionieren:  
  
 [!CODE [NVC_MFC_CListBox#48](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_CListBox#48)]  
  
## Siehe auch  
 [BEGIN\_TEMPLATE\_MESSAGE\_MAP](../Topic/BEGIN_TEMPLATE_MESSAGE_MAP.md)   
 [Meldungsbehandlung und \-zuordnung](../mfc/message-handling-and-mapping.md)