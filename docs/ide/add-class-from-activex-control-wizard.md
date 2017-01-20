---
title: "Hinzuf&#252;gen einer Klasse mit dem ActiveX-Steuerelement-Assistenten"
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
  - "vc.codewiz.class.axcontrol"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX-Steuerelement-Assistent"
  - "Assistent zum Hinzufügen von Klassen aus ActiveX-Steuerelementen [C++]"
ms.assetid: 668d801c-5fb6-4176-9191-5c38995a4713
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Hinzuf&#252;gen einer Klasse mit dem ActiveX-Steuerelement-Assistenten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Mit diesem Assistenten können Sie eine MFC\-Klasse aus einem verfügbaren ActiveX\-Steuerelement hinzufügen.  Für jede Schnittstelle, die Sie aus dem ausgewählten ActiveX\-Steuerelement hinzufügen, erstellt der Assistent eine Klasse.  
  
 **Klasse einfügen von**  
 Gibt den Speicherort der Typbibliothek an, aus der die Klasse erstellt wird.  
  
|Option|Beschreibung|  
|------------|------------------|  
|**Registrierung**|Die Typbibliothek ist im System registriert.  Registrierte Typbibliotheken sind unter **Verfügbare ActiveX\-Steuerelemente** aufgeführt.|  
|**Datei**|Die Typbibliothek muss nicht unbedingt im System registriert sein, sie ist jedoch in einer Datei enthalten.  Das Verzeichnis der Datei muss unter **Speicherort** angegeben werden.|  
  
 **Verfügbare ActiveX\-Steuerelemente**  
 Gibt die ActiveX\-Steuerelemente an, die derzeit im System registriert sind.  Wählen Sie in dieser Liste ein ActiveX\-Steuerelement aus, um die dazugehörigen Schnittstellen in der Liste **Schnittstellen** anzuzeigen.  Weitere Informationen zum Registrieren von ActiveX\-Steuerelementen finden Sie unter [MFC\-ActiveX\-Steuerelemente: Weitergabe von ActiveX\-Steuerelementen](../mfc/mfc-activex-controls-distributing-activex-controls.md).  
  
 Wenn Sie unter **Klasse einfügen von** auf **Datei** klicken, kann dieses Feld nicht bearbeitet werden.  
  
 **Speicherort**  
 Gibt den Speicherort des ActiveX\-Steuerelements an.  Wenn Sie unter **Klasse einfügen von** auf **Datei** klicken, können Sie den Speicherort der Datei angeben, die die Typbibliothek enthält.  Um nach dem Speicherort der Datei zu suchen, klicken Sie auf die Schaltfläche mit den Auslassungspunkten \(...\).  
  
 Wenn Sie unter **Klasse einfügen von** auf **Registrierung** klicken, kann dieses Feld nicht bearbeitet werden.  
  
 **Schnittstellen**  
 Legt die Schnittstellen im ActiveX\-Steuerelement fest, das derzeit unter Verfügbare ActiveX\-Steuerelemente oder in der Typbibliothek in der unter **Speicherort** angegebenen Datei markiert ist.  
  
|Übertragungsschaltfläche|Beschreibung|  
|------------------------------|------------------|  
|**\>**|Fügt die Schnittstelle hinzu, die derzeit in der Liste **Schnittstellen** markiert ist.  Wenn keine Schnittstelle markiert ist, ist die Schaltfläche nicht verfügbar.|  
|**\>\>**|Fügt alle Schnittstellen hinzu, die im derzeit unter Verfügbare ActiveX\-Steuerelemente markierten ActiveX\-Steuerelement oder in der Typbibliothek der Datei, die unter **Speicherort** angegeben ist, enthalten sind.|  
|**\<**|Entfernt die derzeit markierte Klasse aus der Liste **Generierte Klassen**.  Falls in der Liste **Generierte Klassen** keine Klasse markiert ist, ist die Schaltfläche nicht verfügbar.|  
|**\<\<**|Entfernt alle Klassen aus der Liste **Generierte Klassen**.  Wenn die Liste **Generierte Klassen** leer ist, ist die Schaltfläche nicht verfügbar.|  
  
 **Generierte Klassen**  
 Legt die Klassennamen fest, die mithilfe der Schnittstellen, die über die Schaltfläche **\>** oder **\>\>** hinzugefügt wurden, generiert werden.  Um eine Klasse auszuwählen, können Sie auf dieses Feld klicken und dann mit der NACH\-OBEN\- oder NACH\-UNTEN\-TASTE in der Liste einen Bildlauf durchführen. Dabei werden im Feld **Klasse** die einzelnen Klassennamen und im Feld **.h\-Datei** die einzelnen Dateinamen angezeigt, die vom Assistenten erstellt werden, nachdem Sie auf **Fertig stellen** geklickt haben.  In diesem Feld kann jeweils nur eine Klasse markiert werden.  
  
 Sie können eine Klasse entfernen, indem Sie sie in dieser Liste markieren und auf **\<** klicken.  Um alle Klassen zu entfernen, ist es nicht erforderlich, im Feld **Generierte Klassen** Klassen zu markieren. Wenn Sie auf **\<\<** klicken, werden alle Klassen aus dem Feld **Generierte Klassen** gelöscht.  
  
 `Class`  
 Gibt den Namen der im Feld **Generierte Klassen** ausgewählten Klasse an, die vom Assistenten hinzugefügt wird, nachdem Sie auf **Fertig stellen** geklickt haben.  Sie können den Namen im Feld **Klasse** bearbeiten.  
  
 **.h\-Datei**  
 Legt den Namen der Headerdatei für die neue Objektklasse fest.  Dieser Name basiert standardmäßig auf dem Namen, den Sie unter **Generierte Klassen** angeben.  Klicken Sie auf die Schaltfläche mit den Auslassungspunkten \(...\), um den Dateinamen am gewünschten Speicherort zu speichern oder um die Klassendeklaration an eine vorhandene Datei anzufügen.  Wenn Sie eine vorhandene Datei auswählen, wird sie vom Assistenten erst am ausgewählten Speicherort gespeichert, nachdem Sie im Assistenten auf **Fertig stellen** geklickt haben.  
  
 Der Assistent ist nicht in der Lage, Dateien zu überschreiben.  Wenn Sie den Namen einer vorhandenen Datei auswählen und dann auf **Fertig stellen** klicken, wird vom Assistenten eine Bestätigung angefordert, die Klassendeklaration an den Inhalt der Datei anzufügen.  Klicken Sie auf **Ja**, um die Datei anzufügen, und klicken Sie auf **Nein**, um zum Assistenten zurückzukehren und einen anderen Dateinamen anzugeben.  
  
 **.cpp\-Datei**  
 Legt für die neue Objektklasse den Namen der Implementierungsdatei fest.  Dieser Name basiert standardmäßig auf dem Namen, den Sie unter **Generierte Klassen** angeben.  Klicken Sie auf die Schaltfläche mit den Auslassungspunkten \(...\), um den Dateinamen am gewünschten Speicherort zu speichern.  Die Datei wird erst am ausgewählten Speicherort gespeichert, wenn Sie im Assistenten auf **Fertig stellen** klicken.  
  
 Der Assistent ist nicht in der Lage, Dateien zu überschreiben.  Wenn Sie den Namen einer vorhandenen Datei auswählen und dann auf **Fertig stellen** klicken, werden Sie vom Assistenten gefragt, ob die Klassenimplementierung an den Inhalt der Datei angefügt werden soll.  Klicken Sie auf **Ja**, um die Datei anzufügen, und klicken Sie auf **Nein**, um zum Assistenten zurückzukehren und einen anderen Dateinamen anzugeben.  
  
## Siehe auch  
 [Hinzufügen einer Klasse aus einem ActiveX\-Steuerelement](../ide/adding-a-class-from-an-activex-control-visual-cpp.md)   
 [Automatisierungsclients: Verwenden von Typbibliotheken](../mfc/automation-clients-using-type-libraries.md)