---
title: "Assistent zum Hinzuf&#252;gen von Memberfunktionen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.function.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Asssistent zum Hinzufügen von Memberfunktionen [C++]"
ms.assetid: 13b6defc-faa6-4d57-83db-9dd854cbea3d
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Assistent zum Hinzuf&#252;gen von Memberfunktionen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Assistent fügt der Headerdatei die Deklaration einer Memberfunktion und der Implementierungsdatei der ausgewählten Klasse eine Stub\-Memberfunktion hinzu.  
  
 Nachdem Sie die Memberfunktion mit dem Assistenten hinzugefügt haben, können Sie den Code in der Entwicklungsumgebung bearbeiten.  
  
 **Rückgabetyp**  
 Legt den Rückgabetyp für die hinzugefügte Memberfunktion fest.  Sie können einen eigenen Rückgabetyp angeben oder einen Rückgabetyp aus der Liste der verfügbaren Typen auswählen.  Weitere Informationen zu den Typen finden Sie unter [Grundlegende Typen](../cpp/fundamental-types-cpp.md).  
  
||||  
|-|-|-|  
|`char`|`int`|`unsigned int`|  
|**double**|**long**|`unsigned long`|  
|**float**|**short**|`void`|  
|`HRESULT`|`unsigned char`||  
  
 **Funktionsname**  
 Legt den Namen der Memberfunktion fest, die Sie hinzufügen.  
  
 **Parametertyp**  
 Legt unter der Voraussetzung, dass die Memberfunktion über Parameter verfügt, den Parametertyp fest, den Sie der Memberfunktion hinzufügen.  Sie können einen eigenen Parametertyp angeben oder einen Parametertyp aus der Liste der verfügbaren Typen auswählen.  
  
||||  
|-|-|-|  
|`char`|`int`|`unsigned char`|  
|**double**|**long**|`unsigned int`|  
|**float**|**short**|`unsigned long`|  
  
 **Parametername**  
 Legt unter der Voraussetzung, dass die Memberfunktion über Parameter verfügt, den Namen des Parameters fest, den Sie der Memberfunktion hinzufügen.  
  
 **Parameterliste**  
 Zeigt eine Liste der Parameter an, die Sie der Memberfunktion hinzugefügt haben.  Um der Liste einen Parameter hinzuzufügen, geben Sie einen Typ und Namen in die Felder **Parametertyp** und **Parametername** ein und klicken dann auf **Hinzufügen**.  Um einen Parameter aus der Liste zu entfernen, wählen Sie den Parameter aus und klicken auf **Entfernen**.  
  
 **Zugriff**  
 Legt die Zugriffsebene für die Memberfunktion fest.  Zugriffsmodifizierer sind Schlüsselwörter, die festlegen, welchen Zugriff andere Klassen auf die Memberfunktion haben.  Weitere Informationen zum Festlegen von Zugriffsebenen finden Sie unter [Memberzugriff\-Steuerelement](../cpp/member-access-control-cpp.md).  Die Zugriffsebene für die Memberfunktion ist standardmäßig auf **public** gesetzt.  
  
-   [public](../cpp/public-cpp.md)  
  
-   [protected](../cpp/protected-cpp.md)  
  
-   [private](../cpp/private-cpp.md)  
  
 Prüfen Sie, ob die neue Memberfunktion statisch oder virtuell und ob sie inline oder rein ist.  Wenn Sie die Memberfunktion als reine Funktion festlegen, ist das Kontrollkästchen **Virtuell** aktiviert und das Kontrollkästchen **Inline** nicht verfügbar.  Der Standard ist eine nicht statische, nicht virtuelle Memberfunktion.  
  
|Option|Beschreibung|  
|------------|------------------|  
|[Static](../misc/static-cpp.md)|Legt fest, dass die Funktion global funktioniert und außerhalb der Klasse aufgerufen werden kann. Dies gilt auch, wenn keine Klasseninstanziierung vorhanden ist.  Die Memberfunktion hat keinen Zugriff auf nicht statische Elemente.  Eine mit der Option **Statisch** konfigurierte Memberfunktion kann nicht virtuell sein.|  
|[Virtual](../cpp/virtual-cpp.md)|Stellt sicher, dass die richtige Memberfunktion für ein Objekt aufgerufen wird, und zwar unabhängig von dem Ausdruck, mit dem der Aufruf der Memberfunktion erstellt wurde.  Eine mit der Option **Virtuell** konfigurierte Memberfunktion kann nicht statisch sein.|  
|**Pure**|Gibt an, dass für die deklarierte virtuelle Memberfunktion keine Implementierung zur Verfügung gestellt wird. **Pure** kann aus diesem Grund nur für virtuelle Memberfunktionen festgelegt werden.  Weitere Informationen finden Sie unter [Class\-Member\-Deklarationssyntax](../misc/class-member-declaration-syntax.md).<br /><br /> Eine Klasse, die mindestens eine rein virtuelle Memberfunktion enthält, wird als abstrakte Klasse angesehen.  Klassen, die von der abstrakten Klasse abgeleitet sind, müssen die rein virtuelle Memberfunktion implementieren, um nicht selbst als abstrakte Klasse angesehen zu werden.|  
|[Inline](../cpp/inline-functions-cpp.md)|Weist den Compiler an, eine Kopie des Memberfunktionsrumpfes an jeder Stelle einzufügen, an der die Memberfunktion aufgerufen wird.  Eine mit der Option **Inline** konfigurierte Memberfunktion kann nicht rein sein.|  
  
 **.cpp\-Datei**  
 Legt den Speicherort der Datei fest, in die die Implementierung der Stub\-Memberfunktion geschrieben wird.  Diese Implementierung wird standardmäßig in die CPP\-Datei der Klasse geschrieben, der die Memberfunktion hinzugefügt wird.  Klicken Sie auf die Schaltfläche mit den Auslassungspunkten \(...\), um den Dateinamen zu ändern.  Die Implementierung der Memberfunktion wird dem Inhalt der ausgewählten Datei hinzugefügt.  
  
 **Kommentar**  
 Fügt einen Kommentar für die Memberfunktion in die Headerdatei ein.  
  
 **Funktionssignatur**  
 Zeigt die Memberfunktion so an, wie sie im Code erscheint, nachdem Sie auf **Fertig stellen** geklickt haben.  Text in diesem Feld kann nicht geändert werden.  Um die Memberfunktion zu ändern, bearbeiten Sie die entsprechenden Felder im Assistenten.  
  
## Siehe auch  
 [Hinzufügen einer Memberfunktion](../ide/adding-a-member-function-visual-cpp.md)