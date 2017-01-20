---
title: "Assistent zum Hinzuf&#252;gen von Ereignissen"
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
  - "vc.codewiz.event.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Assistent zum Hinzufügen von Ereignissen [C++]"
ms.assetid: bdd2a7bb-13d5-44d7-abc9-e785ba4e05ce
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Assistent zum Hinzuf&#252;gen von Ereignissen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Mit diesem Assistenten fügen Sie einem MFC\-ActiveX\-Steuerelementprojekt ein Ereignis hinzu.  Sie können ein eigenes Ereignis festlegen, ein typisches vordefiniertes Ereignis anpassen oder aus einer Liste vordefinierter Ereignisse auswählen.  
  
 **Ereignisname**  
 Gibt den Namen an, den Automatisierungsclients verwenden, um ein Ereignis aus der Klasse anzufordern.  Geben Sie einen Namen ein, oder wählen Sie einen Namen aus der Liste aus.  
  
 **Ereignistyp**  
 Gibt den hinzuzufügenden Ereignistyp an.  Diese Option ist nur verfügbar, wenn Sie ein Ereignis aus der Liste **Ereignisname** auswählen.  
  
|Option|Beschreibung|  
|------------|------------------|  
|**Vordefiniert**|Gibt an, dass ein vordefiniertes Ereignis, z. B. das Klicken auf eine Schaltfläche, für diese Klasse implementiert wird.  Vordefinierte Ereignisse sind in der MFC \(Microsoft Foundation Class\)\-Bibliothek definiert.|  
|**Benutzerdefiniert**|Legt fest, dass Sie eine eigene Implementierung des Ereignisses verwenden.|  
  
 **Interner Name**  
 Gibt den Namen der Memberfunktion an, die dieses Ereignis sendet.  Nur für benutzerdefinierte Ereignisse verfügbar.  Der Name basiert auf dem Feld **Ereignisname**.  Sie können den internen Namen ändern, wenn Sie einen anderen als den unter **Ereignisname** angegebenen Namen verwenden möchten.  
  
 **Parametertyp**  
 Legt den Typ des unter **Parametername** angegebenen Parameters fest.  Wählen Sie den Typ aus der Liste aus.  
  
 **Parametername**  
 Legt den Namen eines Parameters fest, der durch das Ereignis übergeben wird.  Nach der Eingabe des Namens müssen Sie auf **Hinzufügen** klicken, um den Namen in die Parameterliste aufzunehmen.  
  
 Nachdem Sie auf **Hinzufügen** geklickt haben, wird der Parametername in der **Parameterliste** angezeigt.  
  
> [!NOTE]
>  Wenn Sie einen Parameternamen angeben und dann zuerst auf **Fertig stellen** anstatt auf **Hinzufügen** klicken, wird der Parameter dem Ereignis nicht hinzugefügt.  In diesem Fall müssen Sie die Methode suchen und den Parameter manuell einfügen. **Parameterliste**  
  
 **add**  
 Fügt den unter **Parametername** angegebenen Parameter mit dem zugehörigen Typ der **Parameterliste** hinzu.  Um einen Parameter in die Liste aufzunehmen, müssen Sie auf **Hinzufügen** klicken.  
  
 **Entfernen**  
 Entfernt den in der **Parameterliste** ausgewählten Parameter aus der Liste.  
  
 **Parameterliste**  
 Zeigt alle Parameter, die der Methode derzeit hinzugefügt sind, mit den zugehörigen Typen an.  Während Sie Parameter hinzufügen, aktualisiert der Assistent die **Parameterliste**, damit jeder Parameter mit dem zugehörigen Typ angezeigt wird.  
  
## Siehe auch  
 [Hinzufügen eines Ereignisses](../ide/adding-an-event-visual-cpp.md)