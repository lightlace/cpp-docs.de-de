---
title: "Gewusst wie: Anpassen der Symbolleiste f&#252;r den Schnellzugriff"
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
  - "Symbolleiste für den Schnellzugriff, Anpassung"
ms.assetid: 2554099b-0c89-4605-9249-31bf9cbcefe0
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Anpassen der Symbolleiste f&#252;r den Schnellzugriff
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Symbolleiste für den Schnellzugriff \(QAT\) ist eine anpassbare Symbolleiste, die einen Satz Befehle enthält, die entweder sind, neben der Anwendungsschaltfläche oder unter den Kategorienregisterkarten angezeigt wird.  Die folgende Abbildung zeigt eine typische Symbolleiste für den Schnellzugriff an.  
  
 ![MFC&#45;Menübandsymbolleiste für den Schnellzugriff](../mfc/media/quick_access_toolbar.png "Quick\_Access\_Toolbar")  
  
 Um die Symbolleiste für den Schnellzugriff anzupassen, öffnen Sie sie im Fenster **Eigenschaften**, ändern Sie seine Befehle, und zeigen Sie das Menüband in der Vorschau.  
  
### So die Symbolleiste für den Schnellzugriff im Eigenschaftenfenster öffnen  
  
1.  In Visual Studio im Menü **Ansicht**, klicken Sie auf **Ressourcenansicht**.  
  
2.  Doppelklicken Sie in **Ressourcenansicht** auf die Menübandressource, um sie auf der Entwurfsoberfläche anzuzeigen.  
  
3.  Auf Entwurfsoberfläche klicken Sie auf das Schnellzugriff\-Menü Symbolleiste für den mit der rechten Maustaste und klicken Sie dann auf **Eigenschaften**.  
  
## Symbolleiste für den Schnellzugriff\-Eigenschaften  
 In der folgenden Tabelle definiert die Eigenschaften der Symbolleiste für den Schnellzugriff.  
  
|Eigenschaft|Definition|  
|-----------------|----------------|  
|QAT\-Position|Gibt die Position der Symbolleiste für den Schnellzugriff beim Start der Anwendung an.  Die Position kann entweder **Oberhalb** oder **Unterhalb** sein das Menüband.|  
|QAT\-Elemente|Gibt die Befehle an, die für die Symbolleiste für den Schnellzugriff verfügbar sind.|  
  
#### Um Befehle auf der Symbolleiste für den Schnellzugriff hinzufügen oder entfernen  
  
1.  Im Fenster **Eigenschaften** klicken Sie auf **QAT\-Elemente** und klicken Sie auf die Schaltfläche mit den Auslassungspunkten **\(...\)**.  
  
2.  Im Dialogfeld **QAT\-Element\-Editor** verwenden Sie die Schaltflächen **Hinzufügen** und **Entfernen**, um die Liste von Befehlen auf der Symbolleiste für den Schnellzugriff zu ändern.  
  
3.  Wenn Sie einen Befehl möchten, auf der Symbolleiste für den Schnellzugriff und der Symbolleiste für den Schnellzugriff\-Menü angezeigt wird, wählen Sie das Kontrollkästchen neben dem Befehl aus.  Wenn Sie den Befehl soll, nur im Menü angezeigt wird, deaktivieren Sie das Feld.  
  
## Vorschaufunktion des Menübands  
 Symbolleiste für den Schnellzugriff\-Befehle werden nicht auf der Entwurfsoberfläche.  Um diese anzuzeigen, müssen Sie entweder dieses Menüband in der Vorschau anzeigen bzw. die Anwendung ausführen.  
  
#### So das Menüband in der Vorschau anzeigen  
  
-   Klicken Sie auf der **Menüband\-Editor\-SymbolleisteRibbon testen**.  
  
## Siehe auch  
 [Menüband\-Designer \(MFC\)](../mfc/ribbon-designer-mfc.md)