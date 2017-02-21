---
title: "Hinzuf&#252;gen einer Eigenschaft zum Steuerelement (ATL-Lernprogramm, Teil 3) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
ms.assetid: f775fe34-103b-4f07-9999-400e987ee030
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Hinzuf&#252;gen einer Eigenschaft zum Steuerelement (ATL-Lernprogramm, Teil 3)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`IPolyCtl` ist die Schnittstelle, die die benutzerdefinierten Methoden und die Eigenschaften des Steuerelements enthält, und Sie fügen eine Eigenschaft hinzu.  
  
### So legen Sie eine Eigenschaft mit dem Assistenten zum Hinzufügen von Eigenschaften hinzufügen  
  
1.  Erweitern Sie in der Klassenansicht die Polygonverzweigung.  
  
2.  Klicken Sie auf IPolyCtl mit der rechten Maustaste.  
  
3.  Klicken Sie im Kontextmenü **Hinzufügen** klicken Sie auf und dann auf **Eigenschaft hinzufügen**.  
  
     Der Assistent zum Hinzufügen von Eigenschaften angezeigt wird.  
  
4.  In der Dropdownliste von Eigenschaftentypen, wählen Sie `SHORT`.  
  
5.  Typ `Seiten` als **Eigenschaftenname.**  
  
6.  Klicken Sie auf die Eigenschaft hinzuzufügen, zu beenden **Fertig stellen**.  
  
 Wenn Sie die Eigenschaft der Schnittstelle hinzufügen, definiert MIDL \(das Programm, das .idl\-Dateien kompiliert\), eine `Get`\-Methode zum Abrufen des Werts und eine `Put`\-Methode zum Festlegen eines neuen Werts.  Die Methoden werden benannt, indem `put_` und `get_` dem Eigenschaftennamen vorangestellt wird.  
  
 Der Assistent zum Hinzufügen von Eigenschaften fügt die erforderlichen Zeilen der IDL\-Datei hinzu.  Es wird auch die `Get` und `Put`\-Funktionsprototypen der Klassendefinition in PolyCtl.h hinzu und fügt eine leere Implementierung PolyCtl.cpp hinzu.  Sie können dies überprüfen, indem Sie PolyCtl.cpp öffnen und nach den Funktionen `get_Sides` und `put_Sides` suchen.  
  
 Obwohl Sie jetzt die Skelettfunktionen haben, zum Festlegen der Eigenschaft und abzurufen, erfordert sie einen Platz, gespeichert werden.  Sie erstellen eine Variable, um die Eigenschaft zu speichern und die Funktionen entsprechend zu aktualisieren.  
  
#### So erstellen Sie eine Variable, um die Eigenschaft zu speichern und vorbereitet aktualisieren und Methoden abzurufen  
  
1.  Im Projektmappen\-Explorer fügen geöffnete PolyCtl.h und die folgende Zeile nach der Definition von `m_clrFillColor` hinzu:  
  
     [!CODE [NVC_ATL_Windowing#44](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#44)]  
  
2.  Legen Sie den Standardwert von `m_nSides` fest.  Führen Sie die standardmäßige Form ein Dreieck, indem Sie eine Zeile an den Konstruktor in PolyCtl.h hinzufügen:  
  
     [!CODE [NVC_ATL_Windowing#45](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#45)]  
  
3.  Implementieren Sie die `Get`\-Methode und die `Put`\-Methode.  Die `get_Sides` und `put_Sides`\-Funktionsdeklarationen sind zu PolyCtl.h hinzugefügt.  Ersetzen Sie den Code in PolyCtl.cpp für `get_Sides` und in `put_Sides` durch folgenden Code:  
  
     [!CODE [NVC_ATL_Windowing#46](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#46)]  
  
 Die `get_Sides`\-Methode gibt den aktuellen Wert der `Sides`\-Eigenschaft durch den `pVal` Zeiger zurück.  In der `put_Sides`\-Methode erstellt der Code sicher, dass der Benutzer die `Sides`\-Eigenschaft einen zulässigen Wert festgelegt wird.  Das Minimum muss 2 und da ein Array aus Punkten für jede Seite verwendet wird, 100 sein ist eine angemessene Grenzwert für einen Höchstwert.  
  
 Sie verfügen jetzt über eine Eigenschaft, die `Sides` aufgerufen wird.  Im nächsten Schritt ändern Sie den Zeichencode, ihn zu verwenden.  
  
 [Zurück zu Schritt 2](../atl/adding-a-control-atl-tutorial-part-2.md) &#124; [Klicken Sie zu Schritt 4](../atl/changing-the-drawing-code-atl-tutorial-part-4.md)  
  
## Siehe auch  
 [Lernprogramm](../atl/active-template-library-atl-tutorial.md)