---
title: "Adding Connection Points to an Object"
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
  - "Verbindungspunkte [C++], Hinzufügen zu ATL-Objekten"
  - "Implement Connection Point ATL wizard"
ms.assetid: 843531be-4a36-4db0-9d54-e029b1a72a8b
caps.latest.revision: 12
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Adding Connection Points to an Object
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[ATL\-Lernprogramm](../atl/active-template-library-atl-tutorial.md) zeigt, wie ein Steuerelement mit Unterstützung für Verbindungspunkte erstellt, wie Ereignisse und dann hinzufügen, wie Sie den Verbindungspunkt implementiert.  ATL implementiert Verbindungspunkte mit der [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md)\-Klasse.  
  
 Um einen Verbindungspunkt implementieren, haben Sie zwei Möglichkeiten:  
  
-   Implementieren Sie Ihre eigene Verbindungen Ereignisquelle, indem Sie einen Verbindungspunkt zum \- Steuerelement oder dem Objekt hinzufügen.  
  
-   Verwenden Sie eine Verbindungspunkt\-Schnittstelle erneut, die in einer anderen Typbibliothek definiert wird.  
  
 In beiden Fällen verwendet der Assistent zum Implementieren von Verbindungspunkten eine Typbibliothek, um ihre Aufgaben auszuführen.  
  
### So fügen Sie einen Verbindungspunkt zu einem Steuerelement hinzufügen oder Objekt  
  
1.  Definieren Sie eine Dispatchschnittstelle im Library\-Block der IDL\-Datei.  Wenn Sie Unterstützung für Verbindungspunkte aktivierten, als Sie das Steuerelement mit dem ATL\-Steuerelement\-Assistenten erstellt haben, wird die Dispatchschnittstelle bereits erstellt.  Wenn Sie keine Unterstützung für Verbindungspunkte aktivierten, als Sie das Steuerelement erstellt haben, müssen Sie eine Dispatchschnittstelle der IDL\-Datei manuell hinzufügen.  Im folgenden Beispiel einer Dispatchschnittstelle.  Ausgangsschnittstellen ist nicht erforderlich, Dispatchschnittstellen sein, sondern viele Skriptsprachen wie VBScript und JScript benötigen dieses, sodass Verwendung dieses Beispiels zwei Dispatchschnittstellen:  
  
     [!CODE [NVC_ATL_Windowing#81](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#81)]  
  
     Verwenden Sie entweder das uuidgen.exe oder guidgen.exe\-Hilfsprogramm, um ein GUID zu generieren.  
  
2.  Fügen Sie die Dispatchschnittstelle als die `[default,source]`\-Schnittstelle in der Co\-Klasse für das Objekt in die IDL\-Datei des Projekts hinzu.  Auch wenn Sie Unterstützung für Verbindungspunkte aktivierten, als Sie das Steuerelement erstellt haben, erstellt der ATL\-Steuerelement\-Assistent den `[default,source`\] Eintrag.  Um diesen Eintrag manuell hinzuzufügen, fügen Sie die Zeile fett hinzu:  
  
     [!CODE [NVC_ATL_Windowing#82](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#82)]  
  
     Siehe die IDL\-Datei im [Circ](../top/visual-cpp-samples.md) ATL, als ein Beispiel zu überprüfen.  
  
3.  Verwenden Sie die Klassenansicht, um Methoden und Eigenschaften der Ereignisschnittstelle hinzuzufügen.  Klicken Sie auf die Klasse in der Klassenansicht mit der rechten Maustaste, zeigen Sie auf **Hinzufügen** im Kontextmenü auf, und klicken Sie auf **HinzufügenConnection Point**.  
  
4.  Im **Quellschnittstellen** Listenfeld des Assistenten zum Implementieren von Verbindungspunkten, wählen Sie **Schnittstellen des Projekts**.  Wenn Sie eine Schnittstelle für das Steuerelement und die **OK** auswählen, werden Sie:  
  
    -   Generieren Sie eine Headerdatei mit einer Ereignisproxyklasse, die den Code implementiert, der die ausgehenden ruft für das Ereignis macht.  
  
    -   Fügen Sie einen Eintrag der Verbindungspunktzuordnung hinzu.  
  
     Sie sehen auch eine Liste aller Typbibliotheken auf dem Computer.  Sie sollten eine dieser anderen diese nur verwenden, um den Verbindungspunkt zu definieren, wenn Sie das genaue implementieren möchten die gleiche Ausgangsschnittstelle, die in einer anderen Typbibliothek gefunden wird.  
  
### So fügen Sie eine Verbindungspunkt\-Schnittstelle wiederverwenden definiert in eine andere Typbibliothek  
  
1.  Klicken Sie in der Klassenansicht auf eine Klasse, die ein **BEGIN\_COM\_MAP**\-Makro implementiert, zeigen Sie auf **Hinzufügen** im Kontextmenü und klicken auf **HinzufügenConnection Point** mit der rechten Maustaste.  
  
2.  Im Assistenten zum Implementieren von Verbindungspunkten wählen Sie eine Typbibliothek und eine Schnittstelle in der Typbibliothek aus und klicken Sie auf **Hinzufügen**.  
  
3.  Bearbeiten Sie die IDL\-Datei zu einem:  
  
    -   Kopieren Sie die Dispatchschnittstelle aus der IDL\-Datei des Objekts, dessen Ereignisquelle verwendet wird.  
  
    -   Verwenden Sie die **importlib**\-Anweisung auf dieser Typbibliothek.  
  
## Siehe auch  
 [Verbindungspunkt](../atl/atl-connection-points.md)