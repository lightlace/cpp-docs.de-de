---
title: "Assistent zum Hinzuf&#252;gen von Klassen aus der Typbibliothek | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.class.typelib"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Assistent zum Hinzufügen von Klassen aus der Typbibliothek [C++]"
  - "COM-Schnittstellen, Hinzufügen von Klassen"
ms.assetid: 96152afd-9374-4649-a6ab-b0fa2a5592a3
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Assistent zum Hinzuf&#252;gen von Klassen aus der Typbibliothek
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Mit diesem Assistenten können Sie eine MFC\-Klasse aus einer verfügbaren Typbibliothek hinzufügen.  Der Assistent erstellt für jede Schnittstelle, die Sie aus der ausgewählten Typbibliothek hinzufügen, eine Klasse.  
  
 **Klasse einfügen von**  
 Gibt den Speicherort der Typbibliothek an, aus der die Klasse erstellt wird.  
  
|Option|**Beschreibung**|  
|------------|----------------------|  
|**Registrierung**|Die Typbibliothek ist im System registriert.  Registrierte Typbibliotheken sind unter **Verfügbare Typbibliotheken** aufgeführt.|  
|**Datei**|Die Typbibliothek muss nicht unbedingt im System registriert sein, sie ist jedoch in einer Datei enthalten.  Das Verzeichnis der Datei muss unter **Speicherort** angegeben werden.|  
  
 **Verfügbare Typbibliotheken**  
 Listet die Typbibliotheken auf, die derzeit im System registriert sind.  Wählen Sie eine Typbibliothek aus dieser Liste aus, um die dazugehörigen Schnittstellen in der Liste **Schnittstellen** anzuzeigen.  
  
 Weitere Informationen zur Registrierung von Typbibliotheken finden Sie in der MSDN Library unter "Inside Distributed COM: Type Libraries and Language Integration".  
  
 **Speicherort**  
 Gibt den Speicherort der Typbibliothek an.  Wenn Sie unter **Klasse einfügen von** auf **Datei** klicken, können Sie den Speicherort der Datei angeben, die die Typbibliothek enthält.  Um nach dem Speicherort der Datei zu suchen, klicken Sie auf die Schaltfläche mit den Auslassungspunkten \(...\).  
  
 **Schnittstellen**  
 Listet die Schnittstellen auf, die in der derzeit unter **Verfügbare Typbibliotheken** markierten Typbibliothek verfügbar sind.  
  
|Übertragungsschaltfläche|**Beschreibung**|  
|------------------------------|----------------------|  
|**\>**|Fügt die Schnittstelle hinzu, die derzeit in der Liste **Schnittstellen** markiert ist.  Die Schaltfläche ist abgeblendet, falls keine Schnittstelle markiert ist.|  
|**\>\>**|Fügt alle Schnittstellen aus der Typbibliothek hinzu, die derzeit unter **Verfügbare Typbibliotheken** markiert sind.|  
|**\<**|Entfernt die derzeit markierte Klasse aus der Liste **Generierte Klassen**.  Die Schaltfläche ist abgeblendet, falls derzeit keine Klasse in der Liste **Generierte Klassen** markiert ist.|  
|**\<\<**|Entfernt alle Klassen aus der Liste **Generierte Klassen**.  Die Schaltfläche ist abgeblendet, wenn die Liste **Generierte Klassen** leer ist.|  
  
 **Generierte Klassen**  
 Gibt den an der Schnittstellen generiert werden Klassennamen, die mit der **\>** oder **\>\>** Schaltfläche hinzugefügt werden.  Zum Auswählen einer Klasse können Sie auf dieses Feld klicken und dann mit der NACH\-OBEN\- oder NACH\-UNTEN\-TASTE einen Bildlauf in der Liste durchführen. Dabei werden die einzelnen Klassennamen und Dateinamen, die vom Assistenten generiert werden, nachdem Sie auf **Fertig stellen** geklickt haben, im Feld **Klasse** bzw. im Feld **Datei** angezeigt.  In diesem Feld kann jeweils nur eine Klasse markiert werden.  
  
 Sie können eine Klasse entfernen, indem Sie diese in der Liste auswählen und auf **\<** klicken.  Sie müssen nicht, um eine Klasse im generierten Klassenfeld auszuwählen, um alle Klassen zu entfernen; indem Sie auf **\<\<** klicken, entfernen Sie alle Klassen im **Generierte Klassen** \- Feld.  
  
 `Class`  
 Gibt den Namen der im Feld **Generierte Klassen** ausgewählten Klasse an, die vom Assistenten hinzugefügt wird, nachdem Sie auf **Fertig stellen** geklickt haben.  Sie können den Namen im Feld **Klasse** bearbeiten.  
  
 **Datei**  
 Legt den Namen der Headerdatei für die neue Klasse fest.  Dieser Name basiert standardmäßig auf dem Namen, den Sie unter **Generierte Klassen** angeben.  Klicken Sie auf die Schaltfläche mit den Auslassungspunkten \(...\), um den Dateinamen am gewünschten Speicherort zu speichern oder um die Klassendeklaration an eine vorhandene Datei anzufügen.  Wenn Sie eine vorhandene Datei auswählen, wird sie vom Assistenten erst am ausgewählten Speicherort gespeichert, nachdem Sie im Assistenten auf **Fertig stellen** geklickt haben.  
  
 Der Assistent ist nicht in der Lage, Dateien zu überschreiben.  Wenn Sie den Namen einer vorhandenen Datei auswählen und dann auf **Fertig stellen** klicken, wird vom Assistenten eine Bestätigung angefordert, die Klassendeklaration an den Inhalt der Datei anzufügen.  Klicken Sie auf **Ja**, um die Datei anzufügen, und klicken Sie auf **Nein**, um zum Assistenten zurückzukehren und einen anderen Dateinamen anzugeben.  
  
## Siehe auch  
 [MFC\-Klasse aus einer Typbibliothek](../../mfc/reference/adding-an-mfc-class-from-a-type-library.md)   
 [Automatisierungsclients: Verwenden von Typbibliotheken](../../mfc/automation-clients-using-type-libraries.md)