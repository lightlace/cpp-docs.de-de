---
title: 'MFC-ActiveX-Steuerelemente: Hinzufügen von benutzerdefinierten Eigenschaften | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], properties
- properties [MFC], custom
ms.assetid: 85af5167-74c7-427b-b8f3-e0d7b73942e5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fc3aa3f7aa8b6f4abf28c12a11f75540f59238e4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="mfc-activex-controls-adding-custom-properties"></a>MFC-ActiveX-Steuerelemente: Hinzufügen von benutzerdefinierten Eigenschaften
Benutzerdefinierte Eigenschaften unterscheiden sich von Basiseigenschaften, benutzerdefinierte Eigenschaften von noch nicht implementiert werden, die `COleControl` Klasse. Eine benutzerdefinierte Eigenschaft wird verwendet, um einen bestimmten Zustand oder die Darstellung eines ActiveX-Steuerelements an ein Programmierer, die mithilfe des Steuerelements verfügbar zu machen.  
  
 In diesem Artikel wird beschrieben, wie eine benutzerdefinierte Eigenschaft hinzufügen, um das ActiveX-Steuerelement mithilfe des Assistenten zum Hinzufügen von Eigenschaften und erläutert, die sich ergebende codeänderungen. Folgende Themen werden behandelt:  
  
-   [Verwenden den Assistenten zum Hinzufügen einer Eigenschaft zum Hinzufügen von einer benutzerdefinierten Eigenschaft](#_core_using_classwizard_to_add_a_custom_property)  
  
-   [Fügen Sie der Assistent zum Eigenschaften Änderungen für benutzerdefinierte Eigenschaften hinzu](#_core_classwizard_changes_for_custom_properties)  
  
 Benutzerdefinierte Eigenschaften sind in vier Arten von Implementierung: Membervariable, Membervariable mit Benachrichtigung, Get/Set-Methoden und parametrisiert.  
  
-   Variable Schnittstellenmember-Implementierung  
  
     Diese Implementierung der Zustand der Eigenschaft, die als eine Membervariable in der Control-Klasse dargestellt wird. Verwenden Sie die Membervariablen Implementierung aus, wenn es nicht wichtig zu wissen, wenn der Eigenschaftswert geändert wird. Die drei Typen erstellt diese Implementierung geringstem Unterstützungscode für die Eigenschaft. Die Verteilung Zuordnung Eintrag Makro für Variable Schnittstellenmember-Implementierung ist [DISP_PROPERTY](../mfc/reference/dispatch-maps.md#disp_property).  
  
-   Membervariablen mit Notification-Implementierung  
  
     Diese Implementierung besteht aus einer Membervariablen gespeichert und eine Benachrichtigungsfunktion, die durch den Assistenten zum Hinzufügen einer Eigenschaft erstellt. Die Benachrichtigungsfunktion wird nach der Eigenschaftswert ändert automatisch vom Framework aufgerufen. Verwenden Sie die Membervariablen mit Notification-Implementierung, wenn Sie benachrichtigt werden, nachdem ein Eigenschaftswert geändert wurde, müssen. Diese Implementierung benötigt mehr Zeit, da es sich um einen Funktionsaufruf erfordert. Die Dispatch-Zuordnungsmakros Eintrag für diese Implementierung ist [DISP_PROPERTY_NOTIFY](../mfc/reference/dispatch-maps.md#disp_property_notify).  
  
-   Get/Set-Methoden-Implementierung  
  
     Diese Implementierung besteht aus einem Paar von Memberfunktionen in der Control-Klasse. Die Get/Set-Methoden Implementierung ruft automatisch den Get-Member-Funktion, wenn der Benutzer des Steuerelements den aktuellen Wert der Eigenschaft anfordert und die Set-Memberfunktion, wenn der Benutzer des Steuerelements angefordert wird, dass die Eigenschaft geändert werden. Verwenden Sie diese Implementierung, wenn Sie benötigen zum Berechnen des Werts einer Eigenschaft während der Laufzeit einen vom Benutzer des Steuerelements vor dem Ändern der tatsächliche Eigenschaft übergebenen Wert überprüfen, oder implementieren einen Eigenschaftstyp Lese- oder Schreibzugriff nur. Die Dispatch-Zuordnungsmakros Eintrag für diese Implementierung ist [DISP_PROPERTY_EX](../mfc/reference/dispatch-maps.md#disp_property_ex). Im folgenden Abschnitt [mithilfe des Assistenten zum Hinzufügen von Eigenschaften zum Hinzufügen einer benutzerdefinierten Eigenschaft](#_core_using_classwizard_to_add_a_custom_property), verwendet die benutzerdefinierte CircleOffset-Eigenschaft, um diese Implementierung zu veranschaulichen.  
  
-   Parametrisierte Implementierung  
  
     Parametrisierte Implementierung wird von den Assistenten zum Hinzufügen einer Eigenschaft unterstützt. Eine parametrisierte Eigenschaft (manchmal eine Array-Eigenschaft genannt) kann verwendet werden, um einen Satz von Werten über eine einzelne Eigenschaft des Steuerelements zugreifen. Die Dispatch-Zuordnungsmakros Eintrag für diese Implementierung ist `DISP_PROPERTY_PARAM`. Weitere Informationen zum Implementieren dieses Typs finden Sie unter [Implementieren einer parametrisierten Eigenschaft](../mfc/mfc-activex-controls-advanced-topics.md) Artikel ActiveX-Steuerelemente: Weiterführende Themen.  
  
##  <a name="_core_using_classwizard_to_add_a_custom_property"></a> Mithilfe der Eigenschaft Assistenten zum Hinzufügen zum Hinzufügen einer benutzerdefinierten Eigenschaft  
 Das folgende Verfahren veranschaulicht das Hinzufügen einer benutzerdefinierten Eigenschaft, CircleOffset, die die Implementierung der Get/Set-Methoden verwendet. Die benutzerdefinierte CircleOffset-Eigenschaft kann Benutzer für den Kreis vom Mittelpunkt des umschließenden Rechtecks des Steuerelements den offset des Steuerelements. Das Verfahren zum Hinzufügen von benutzerdefinierten Eigenschaften mit einer Implementierung als Get/Set-Methoden ist sehr ähnlich.  
  
 Dasselbe Verfahren kann auch verwendet werden, andere benutzerdefinierten Eigenschaften hinzufügen, die Sie möchten. Verwenden Sie den benutzerdefinierten Eigenschaft-Namen für die CircleOffset Eigenschaftennamen und die Parameter an.  
  
#### <a name="to-add-the-circleoffset-custom-property-using-the-add-property-wizard"></a>Die benutzerdefinierte CircleOffset-Eigenschaft, die mithilfe des Assistenten zum Hinzufügen von Eigenschaften hinzufügen  
  
1.  Laden Sie das Steuerelementprojekt.  
  
2.  Erweitern Sie in der Klassenansicht den Bibliotheksknoten des Steuerelements.  
  
3.  Klicken Sie mit der rechten Maustaste auf den Schnittstellenknoten des Steuerelements (den zweiten Knoten des Bibliotheksknotens), um das Kontextmenü zu öffnen.  
  
4.  Klicken Sie im Kontextmenü auf **hinzufügen** , und klicken Sie dann auf **Eigenschaft hinzufügen**.  
  
     Daraufhin wird die [Assistent zum Hinzufügen von Eigenschaften](../ide/names-add-property-wizard.md).  
  
5.  In der **Eigenschaftsname** geben `CircleOffset`.  
  
6.  Klicken Sie unter **Implementierungstyp**auf **Get/Set-Methoden**.  
  
7.  In der **Eigenschaftentyp** wählen Sie im **kurze**.  
  
8.  Geben Sie eindeutige Namen für die Get- und Set-Funktion, oder übernehmen Sie den Standardnamen.  
  
9. Klicken Sie auf **Fertig stellen**.  
  
##  <a name="_core_classwizard_changes_for_custom_properties"></a> Eigenschaftenänderungen-Assistenten für benutzerdefinierte Eigenschaften hinzufügen  
 Wenn Sie die benutzerdefinierte CircleOffset-Eigenschaft hinzufügen, den Assistenten zum Hinzufügen einer Eigenschaft ändert den Header (. H) und die Implementierung (. CPP) Dateien von der Control-Klasse.  
  
 Die folgenden Zeilen werden hinzugefügt, um die. H-Datei, um zwei aufgerufenen Funktionen deklarieren `GetCircleOffset` und `SetCircleOffset`:  
  
 [!code-cpp[NVC_MFC_AxUI#25](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-properties_1.h)]  
  
 Die folgende Zeile wird dem Steuerelement hinzugefügt. IDL-Datei:  
  
 [!code-cpp[NVC_MFC_AxUI#26](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-properties_2.idl)]  
  
 Diese Zeile weist der CircleOffset-Eigenschaft eine bestimmte ID-Nummer der Position der Methode in der Liste der Methoden und Eigenschaften von den Assistenten zum Hinzufügen einer Eigenschaft entnommen.  
  
 Darüber hinaus wird die folgende Zeile hinzugefügt, um die Dispatchzuordnung (in der. Der Steuerelementklasse CPP-Datei) zum Zuordnen der CircleOffset-Eigenschaft auf das Steuerelement zwei Handlerfunktionen:  
  
 [!code-cpp[NVC_MFC_AxUI#27](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-properties_3.cpp)]  
  
 Schließlich die Implementierungen der `GetCircleOffset` und `SetCircleOffset` Funktionen an das Ende des Steuerelements hinzugefügt werden. CPP-Datei. In den meisten Fällen ändern Sie die Get-Funktion, um den Wert der Eigenschaft zurück. Die Set-Funktion wird in der Regel Code enthalten, die entweder vor oder nach der eigenschaftenänderungen ausgeführt werden soll.  
  
 [!code-cpp[NVC_MFC_AxUI#28](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-properties_4.cpp)]  
  
 Beachten Sie, dass den Assistenten zum Hinzufügen einer Eigenschaft automatisch zu einen Aufruf fügt [SetModifiedFlag](../mfc/reference/colecontrol-class.md#setmodifiedflag), in den Text der Set-Funktion. Das Aufrufen dieser Funktion kennzeichnet das Steuerelement geändert wurde. Wenn ein Steuerelement geändert wurde, wird der neue Zustand gespeichert werden, wenn der Container gespeichert wird. Diese Funktion sollte aufgerufen werden, wenn eine Eigenschaft, die als Teil des persistenten Status des Steuerelements gespeichert Wert ändert.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)   
 [MFC-ActiveX-Steuerelemente: Eigenschaften](../mfc/mfc-activex-controls-properties.md)   
 [MFC-ActiveX-Steuerelemente: Methoden](../mfc/mfc-activex-controls-methods.md)   
 [COleControl-Klasse](../mfc/reference/colecontrol-class.md)
