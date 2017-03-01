---
title: Erweiterte Features, MFC Application Wizard | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.mfc.exe.advanced
dev_langs:
- C++
helpviewer_keywords:
- MFC Application Wizard, advanced features
ms.assetid: 8a6681c5-6576-4b12-841a-6862beee76fa
caps.latest.revision: 17
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: ab9e67efc6fad90f2f9eb140411d063320f09feb
ms.lasthandoff: 02/24/2017

---
# <a name="advanced-features-mfc-application-wizard"></a>Erweiterte Funktionen, MFC-Anwendungs-Assistent
Unter diesem Thema werden die Optionen für zusätzliche Funktionen für Ihre Anwendung aufgeführt, zum Beispiel eine Hilfefunktion, Druckunterstützung usw. Legen Sie in den einzelnen Abschnitten zusätzliche Unterstützungsoptionen für die erweiterten Funktionen fest.  
  
 **Kontextbezogene Hilfe (HTML)**  
 Generiert eine Reihe von Hilfedateien für die kontextbezogene Hilfe über F1 und ein Hilfemenü oder durch Klicken auf eine **Hilfe** Schaltfläche in einem Dialogfeld. Zur Unterstützung der Hilfe ist der Hilfecompiler erforderlich. Sie können den Hilfecompiler nachträglich installieren, indem Sie Setup erneut ausführen.  
  
 Finden Sie unter [HTML-Hilfe: kontextbezogene Hilfe für Programme](../../mfc/html-help-context-sensitive-help-for-your-programs.md) und [Hilfedateien (HTML-Hilfe)](../../ide/help-files-html-help.md) für Weitere Informationen.  
  
 **Drucken und Druckvorschau**  
 Erstellt den Code zur Behandlung der Druck-, druckeinrichtungs- und seitenansichtsbefehle durch Aufrufen von Memberfunktionen in der [CView-Klasse](../../mfc/reference/cview-class.md) der MFC-Bibliothek. Zusätzlich fügt der Assistent dem Anwendungsmenü Befehle für diese Funktionen hinzu. Druckunterstützung steht nur für Programme, die angeben, **von Dokument/Ansicht-Architektur Support** in der [Anwendungstyp, MFC Application Wizard](../../mfc/reference/application-type-mfc-application-wizard.md) Seite des Assistenten. Dokument-/Ansichtsanwendungen verfügen standardmäßig über Druckunterstützung.  
  
 **Automatisierung**  
 Gibt an, dass in der Anwendung Objekte bearbeitet werden können, die in einer anderen Anwendung implementiert wurden, bzw. stellt der Anwendung Automatisierungsclients zur Verfügung.  
  
 **ActiveX-Steuerelemente**  
 Unterstützt ActiveX-Steuerelemente (Standard). Wenn Sie nicht mit dieser Option und einem späteren Zeitpunkt ActiveX-Steuerelemente in das Projekt einfügen möchten, müssen Sie einen Aufruf hinzufügen [AfxEnableControlContainer](http://msdn.microsoft.com/library/7aa0b9d2-5329-4bc3-9d41-856e30fe2c2b) in Ihrer Anwendungsverzeichnis [CWinApp:: InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) Member-Funktion.  
  
 **MAPI (Messaging-API)**  
 Gibt an, dass der Benutzer in der Anwendung E-Mail-Nachrichten erstellen, bearbeiten, übertragen und speichern kann.  
  
 **Windows-sockets**  
 Unterstützt Windows-Sockets, mit denen Sie Anwendungen schreiben können, die über TCP/IP-Netzwerke kommunizieren.  
  
 **Active Accessibility**  
 Bietet Unterstützung für [IAccessible](http://msdn.microsoft.com/library/windows/desktop/dd318466) auf [CWnd](../../mfc/reference/cwnd-class.md)-abgeleiteten Klassen, die Sie zum Anpassen der Benutzeroberfläche für eine bessere Interaktion mit Eingabehilfen-Clients verwenden können.  
  
 **Allgemeines Steuerelementmanifest**  
 Standardmäßig aktiviert. Erstellt ein Anwendungsmanifest zur Aktivierung der im Lieferumfang von Microsoft Windows XP und von neueren Betriebssystemen enthaltenen DLL für allgemeine Steuerelemente.  
  
 Version 6 der DLL für allgemeine Steuerelemente aktualisiert die Vorläuferversion eines allgemeinen Steuerelements, das von einer vorhandenen Anwendung verwendet wird, nicht automatisch. Um die DLL für allgemeine Steuerelemente, Version 6, verwenden zu können, müssen Sie ein Anwendungsmanifest erstellen, das Ihre Anwendung anweist, die neue DLL zu laden. Die DLL für allgemeine Steuerelemente unterstützt auch Windows XP-Designs.  
  
 Durch ein Anwendungsmanifest können auch andere, von Ihrer Anwendung benötigte DLLs und Versionen festgelegt werden. Weitere Informationen über Anwendungsmanifeste finden Sie unter [Isolated Applications and Side-by-Side Assemblies](http://msdn.microsoft.com/library/dd408052) in der [!INCLUDE[winsdkshort](../../atl-mfc-shared/reference/includes/winsdkshort_md.md)].  
  
 **Unterstützung für Neustart-Manager**  
 Fügt Unterstützung für die [Windows-Neustart-Manager](http://msdn.microsoft.com/library/windows/desktop/aa373680\(v=vs.85\).aspx). Dieses Video zeigt, wie Sie den Neustart-Manager von MFC: [How Do I: Use the New Restart Manager](http://msdn.microsoft.com/vstudio/ee886407).  
  
 **Erweiterte Framebereiche**  
 |Option|Beschreibung|  
|------------|-----------------|  
|**Andockbarer Explorer-Bereich**|Erstellt einen andockbaren Bereich, der Visual Studio **Projektmappen-Explorer** links vom Hauptrahmenfenster.|  
|**Andockbarer Ausgabebereich**|Erstellt einen andockbaren Bereich, der Visual Studio **Ausgabe** -Bereich unter dem Hauptrahmenfenster ähnelt.|  
|**Andockbarer Eigenschaftenbereich**|Erstellt einen andockbaren Bereich, der Visual Studio **Eigenschaften** Bereich rechts neben dem Hauptrahmenfenster.|  
|**Navigationsbereich**|Erstellt einen andockbaren Bereich, der der Outlook-Navigationsleiste links vom Hauptrahmenfenster ähnelt.|  
|**Titelleiste**|Erstellt eine Titelleiste im Office-Stil über dem Hauptrahmenfenster.|  
  
 **Anzahl der Dateien in der Liste zuletzt verwendeter Dateien**  
 Gibt die Anzahl der Dateien an, die in der Liste der zuletzt verwendeten Dateien angezeigt werden soll. Die Anzahl beträgt standardmäßig 4.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Anwendung-Assistent](../../mfc/reference/mfc-application-wizard.md)


