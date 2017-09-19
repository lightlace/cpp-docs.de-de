---
title: Erweiterte Features, MFC-Anwendungs-Assistent | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: bb94e24657d16b2a3eda3a770c2b6ae734c6006f
ms.openlocfilehash: 9a291af4641742cd9b771c80a7ea0770fab6de06
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="advanced-features-mfc-application-wizard"></a>Erweiterte Funktionen, MFC-Anwendungs-Assistent
Unter diesem Thema werden die Optionen für zusätzliche Funktionen für Ihre Anwendung aufgeführt, zum Beispiel eine Hilfefunktion, Druckunterstützung usw. Legen Sie in den einzelnen Abschnitten zusätzliche Unterstützungsoptionen für die erweiterten Funktionen fest.  
  
 **Kontextbezogene Hilfe (HTML)**  
 Generiert eine Reihe von Hilfedateien für die kontextbezogene Hilfe über F1 und ein Hilfemenü oder durch Klicken auf eine **Hilfe** Schaltfläche in einem Dialogfeld. Zur Unterstützung der Hilfe ist der Hilfecompiler erforderlich. Sie können den Hilfecompiler nachträglich installieren, indem Sie Setup erneut ausführen.  
  
 Finden Sie unter [HTML-Hilfe: kontextbezogene Hilfe für Programme](../../mfc/html-help-context-sensitive-help-for-your-programs.md) und [Hilfedateien (HTML-Hilfe)](../../ide/help-files-html-help.md) für Weitere Informationen.  
  
 **Drucken und Druckvorschau**  
 Erstellt den Code zur Behandlung der Druck-, druckeinrichtungs- und seitenansichtsbefehle durch Aufrufen von Memberfunktionen in der [CView-Klasse](../../mfc/reference/cview-class.md) aus der MFC-Bibliothek. Zusätzlich fügt der Assistent dem Anwendungsmenü Befehle für diese Funktionen hinzu. Druckunterstützung steht nur für Anwendungen, die angeben, **Unterstützung der Dokument-/Ansichtarchitektur-Architektur** in der [Anwendungstyp, MFC-Anwendungs-Assistent](../../mfc/reference/application-type-mfc-application-wizard.md) Seite des Assistenten. Dokument-/Ansichtsanwendungen verfügen standardmäßig über Druckunterstützung.  
  
 **Automatisierung**  
 Gibt an, dass in der Anwendung Objekte bearbeitet werden können, die in einer anderen Anwendung implementiert wurden, bzw. stellt der Anwendung Automatisierungsclients zur Verfügung.  
  
 **ActiveX-Steuerelemente**  
 Unterstützt ActiveX-Steuerelemente (Standard). Wenn Sie nicht mit dieser Option und einem späteren Zeitpunkt ActiveX-Steuerelemente in Ihrem Projekt einfügen möchten, müssen Sie einen Aufruf von hinzufügen [AfxEnableControlContainer](ole-initialization.md#afxenablecontrolcontainer) in Ihrer Anwendungsverzeichnis [CWinApp:: InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) Memberfunktion.  
  
 **MAPI (Messaging-API)**  
 Gibt an, dass der Benutzer in der Anwendung E-Mail-Nachrichten erstellen, bearbeiten, übertragen und speichern kann.  
  
 **Windows-sockets**  
 Unterstützt Windows-Sockets, mit denen Sie Anwendungen schreiben können, die über TCP/IP-Netzwerke kommunizieren.  
  
 **Active Accessibility**  
 Bietet Unterstützung für [IAccessible](http://msdn.microsoft.com/library/windows/desktop/dd318466) auf [CWnd](../../mfc/reference/cwnd-class.md)-abgeleitete Klassen, die Sie verwenden können, um die Benutzeroberfläche für eine bessere Interaktion mit barrierefreiheitsclients anzupassen.  
  
 **Allgemeines Steuerelementmanifest**  
 Standardmäßig aktiviert. Erstellt ein Anwendungsmanifest zur Aktivierung der im Lieferumfang von Microsoft Windows XP und von neueren Betriebssystemen enthaltenen DLL für allgemeine Steuerelemente.  
  
 Version 6 der DLL für allgemeine Steuerelemente aktualisiert die Vorläuferversion eines allgemeinen Steuerelements, das von einer vorhandenen Anwendung verwendet wird, nicht automatisch. Um die DLL für allgemeine Steuerelemente, Version 6, verwenden zu können, müssen Sie ein Anwendungsmanifest erstellen, das Ihre Anwendung anweist, die neue DLL zu laden. Die DLL für allgemeine Steuerelemente unterstützt auch Windows XP-Designs.  
  
 Durch ein Anwendungsmanifest können auch andere, von Ihrer Anwendung benötigte DLLs und Versionen festgelegt werden. Weitere Informationen über Anwendungsmanifeste finden Sie unter [isolierte Anwendungen und Side-by-Side Assemblys](http://msdn.microsoft.com/library/dd408052) in der [!INCLUDE[winsdkshort](../../atl-mfc-shared/reference/includes/winsdkshort_md.md)].  
  
 **Unterstützung für Neustart-Manager**  
 Fügt Unterstützung für die [Windows-Neustart-Manager](http://msdn.microsoft.com/library/windows/desktop/aa373680\(v=vs.85\).aspx). Dieses Video zeigt, wie die Neustart-Manager von MFC: [wie: Verwenden der neuen Neustart-Managers](http://msdn.microsoft.com/vstudio/ee886407).  
  
 **Erweiterte Framebereiche**  
 |Option|Beschreibung|  
|------------|-----------------|  
|**Andockbarer Explorer-Bereich**|Erstellt einen andockbaren Bereich, der die Visual Studio ähnelt **Projektmappen-Explorer** links vom Hauptrahmenfenster.|  
|**Andockbarer Ausgabebereich**|Erstellt einen andockbaren Bereich, der die Visual Studio ähnelt **Ausgabe** Bereich, der unter dem Hauptrahmenfenster befindet.|  
|**Andockbarer Eigenschaftenbereich**|Erstellt einen andockbaren Bereich, der die Visual Studio ähnelt **Eigenschaften** Bereich rechts vom Hauptrahmenfenster.|  
|**Navigationsbereich**|Erstellt einen andockbaren Bereich, der der Outlook-Navigationsleiste links vom Hauptrahmenfenster ähnelt.|  
|**Titelleiste**|Erstellt eine Titelleiste im Office-Stil über dem Hauptrahmenfenster.|  
  
 **Anzahl der Dateien auf der Liste zuletzt verwendeter Dateien**  
 Gibt die Anzahl der Dateien an, die in der Liste der zuletzt verwendeten Dateien angezeigt werden soll. Die Anzahl beträgt standardmäßig 4.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Anwendungs-Assistent](../../mfc/reference/mfc-application-wizard.md)


