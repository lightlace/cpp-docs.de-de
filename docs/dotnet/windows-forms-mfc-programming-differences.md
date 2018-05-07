---
title: Unterschiede beim Programmieren mit Windows Forms-MFC | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], Windows Forms support
- Windows Forms [C++], compared to MFC
ms.assetid: f3bfcf45-cfd4-45a4-8cde-5f4dbb18ee51
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9ad9e47ba2bb3d9a5e5b21620a4bf4b50177d63b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="windows-formsmfc-programming-differences"></a>Unterschiede beim Programmieren mit Windows Forms und MFC
Die Themen in [Verwenden eines Windows Form-Benutzersteuerelements in MFC](../dotnet/using-a-windows-form-user-control-in-mfc.md) beschreiben die MFC-Unterstützung für Windows Forms. Wenn Sie mit .NET Framework oder MFC nicht vertraut sind, bietet Ihnen dieses Thema Hintergrundinformationen zu den Unterschieden zwischen diesen beiden Arten der Programmierung.  
  
 Windows Forms dient dem Erstellen von Microsoft Windows-Anwendungen in .NET Framework. Dieses Framework stellt eine moderne, objektorientierte und erweiterbare Auswahl von Klassen bereit, mit denen Sie umfangreiche Windows-Anwendungen entwickeln können. Windows Forms bieten die Möglichkeit, eine vielseitige Clientanwendung zu erstellen, die auf eine Vielzahl von Datenquellen zugreifen kann und mithilfe von Windows Forms-Steuerelementen die Datenanzeige und -bearbeitung ermöglicht.  
  
 Wenn Sie jedoch mit MFC vertraut sind, sind Sie es möglicherweise gewohnt, bestimmte Anwendungstypen zu erstellen, die von Windows Forms noch nicht ausdrücklich unterstützt werden. Windows Forms-Anwendungen sind gleichwertig mit MFC-Dialoganwendungen. Sie bieten jedoch nicht die Infrastruktur für die direkte Unterstützung anderer MFC-Anwendungstypen wie OLE-Documentserver/-container oder ActiveX-Dokumente, bzw. zur Unterstützung der Dokument-/Ansichtarchitektur für SDI- (Single-Document Interface), MDI- (Multiple-Document Interface) und MTI-Anwendungen (Multiple Top-Level Interface). Diese Anwendungen können jedoch mithilfe einer selbst programmierten Logik erstellt werden.  
  
 Weitere Informationen zu Windows Forms-Anwendung finden Sie unter [Einführung in Windows Forms](/dotnet/framework/winforms/windows-forms-overview).  
  
 Eine beispielanwendung, die Windows Forms mit MFC verwendet wird, finden Sie unter [MFC und Windows Forms-Integration](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en).  
  
 Zu den folgenden Ansichts- oder Dokument- und Befehlsroutingfunktionen von MFC bestehen keine Äquivalente in Windows Forms:  
  
-   Shellintegration  
  
     Befehle für den dynamischen Datenaustausch (DDE, Dynamic Data Exchange) und Befehlszeilenargumente, die von der Shell verwendet werden, wenn Sie mit der rechten Maustaste auf ein Dokument klicken und Verben wie Öffnen, Bearbeiten oder Drucken auswählen, werden von MFC verarbeitet. Windows Forms bietet keine Shellintegration und reagiert nicht auf Shellverben.  
  
-   Dokumentvorlagen  
  
     In MFC wird eine in einem Rahmenfenster (im MDI-, SDI- oder MTI-Modus) enthaltene Ansicht durch Dokumentvorlagen mit dem geöffneten Dokument verknüpft. Windows Forms bietet kein Äquivalent zu Dokumentvorlagen.  
  
-   Dokumente  
  
     Durch MFC werden Dokumentdateitypen registriert und der Dokumenttyp verarbeitet, sobald ein Dokument über die Shell geöffnet wird. Windows Forms bieten keine Dokumentunterstützung.  
  
-   Dokumentzustand  
  
     Der Änderungszustand eines Dokuments wird von MFC beibehalten. Daher werden Sie von MFC aufgefordert, das Dokument zu speichern, sobald Sie die Anwendung beenden, die letzte Ansicht schließen, in der die Anwendung enthalten ist, oder Windows beenden. Windows Forms bieten keine gleichwertige Unterstützung.  
  
-   Befehle  
  
     Das MFC-Konzept ist befehlsbasiert. Über Menüleiste, Symbolleiste und Kontextmenü können stets dieselben Befehle aufgerufen werden, z. B. Ausschneiden und Kopieren. In Windows Forms sind Befehle eng an Ereignisse eines bestimmten UI-Elements (z. B. eines Menüelements) gebunden, sodass alle Befehlsereignisse explizit verknüpft werden müssen. Mehrere Ereignisse können in Windows Forms auch mit einem einzelnen Handler verarbeitet werden. Weitere Informationen finden Sie unter [Verbinden mehrerer Ereignisse mit einem einzelnen Ereignishandler in Windows Forms](/dotnet/framework/winforms/how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms).  
  
-   Befehlsrouting  
  
     Das MFC-Befehlsrouting ermöglicht die Befehlsverarbeitung durch die aktive Ansicht bzw. das aktive Dokument. Da ein und derselbe Befehl in verschiedenen Ansichten oftmals ein unterschiedliches Verhalten aufweist (Kopieren verhält sich in der Textbearbeitungsansicht anders als in einem Grafikeditor), müssen die Befehle von der aktiven Ansicht verarbeitet werden. Da Windows Forms-Menüs und Symbolleisten keine inhärente Überblick über die aktive Ansicht verfügen, keine unterschiedlichen Handler für die einzelnen Ansichtstypen für Ihre **MenuItem.Click** Ereignisse ohne zusätzlichen internen Code zu schreiben.  
  
-   Mechanismus zur Befehlsaktualisierung  
  
     MFC verfügt über einen Mechanismus zur Befehlsaktualisierung. Aus diesem Grund ist die aktive Ansicht oder das aktive Dokument für den Zustand der Benutzeroberflächenelemente verantwortlich (z. B. das Aktivieren bzw. Deaktivieren eines Menüelements oder einer Symbolleisten-Schaltfläche sowie der Aktivierungsstatus). Windows Forms bieten keinen gleichwertigen Mechanismus für die Befehlsaktualisierung.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden Sie ein Windows Form-Benutzersteuerelements in MFC](../dotnet/using-a-windows-form-user-control-in-mfc.md)   
 [Exemplarische Vorgehensweisen für Windows Forms](http://msdn.microsoft.com/en-us/fd44d13d-4733-416f-aefc-32592e59e5d9)