---
title: ATL-Steuerelement-Assistenten | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.control.overview
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding controls
- controls [ATL], adding to projects
- ATL Control Wizard
ms.assetid: 991f8e72-ffbc-4382-a4ce-e255acfba5b6
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
ms.sourcegitcommit: 4fafe461008e3545243d693e0d9e34acd57163e0
ms.openlocfilehash: 586ac14878ccd6908d025d706b72f3c9856d1b39
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="atl-control-wizard"></a>ATL-Steuerelement-Assistent
Fügt ein ATL-Projekt (oder einem MFC-Projekt mit ATL-Unterstützung) ein ATL-Steuerelement. Mit diesem Assistenten können Sie eine der drei Arten von Steuerelementen einfügen:  
  
-   Standard-Steuerelement  
  
-   Zusammengesetzte Steuerelemente  
  
-   DHTML-Steuerelement  
  
 Sie können angeben ein minimal-Steuerelement, entfernen die Schnittstellen aus der [Schnittstellen](../../atl/reference/interfaces-atl-control-wizard.md) Liste, die standardmäßig für die Steuerelemente in den meisten Containern geöffnet bereitgestellt werden. Sie können festlegen, dass die Schnittstellen, die für das Steuerelement unterstützt werden sollen die **Schnittstellen** Seite des Assistenten.  
  
## <a name="remarks"></a>Hinweise  
 Von diesem Assistenten erstellte Registrierungsskript registriert seine COM-Komponenten unter HKEY_CURRENT_USER anstelle von HKEY_LOCAL_MACHINE. Um dieses Verhalten zu ändern, legen Sie die **Register-Komponente für alle Benutzer** Option des ATL-Assistenten.  
  
## <a name="names"></a>Namen  
 Geben Sie den Namen für das Objekt, die Schnittstelle und die Klassen, die dem Projekt hinzugefügt werden. Mit Ausnahme von **Kurznamen**, alle weiteren Felder unabhängig voneinander geändert werden können. Wenn Sie den Text ändern **Kurznamen**, wirkt sich die Änderung auf die Namen in allen anderen Feldern auf dieser Seite. Wenn Sie ändern die **Co-Klasse** Name im COM-Abschnitt der Änderung wirkt sich die **Typ** Feld jedoch **Schnittstelle** Name und **ProgID** nicht ändern. Dieses Namenssystem ist so ausgelegt, dass alle Namen leicht identifizierbaren für Sie bei der Entwicklung Ihrer Kontrolle.  
  
> [!NOTE]
>  **Coclass** kann nur bei nicht attributierten Steuerelementen bearbeitet werden. Wenn das Projekt über Attribute, kann nicht bearbeitet **Co-Klasse**.  
  
### <a name="c"></a>C++  
 Enthält Informationen über die C++-Klasse erstellt, um das Objekt zu implementieren.  
  
 **Kurzname**  
 Legt den abgekürzten Namen für das Objekt. Der Name, den Sie bestimmt die Klasse und **Coclass** Namen, die Datei (. CPP und. (H) Namen, der Name der Schnittstelle, und die **Typ** Namen, sofern Sie diese Felder einzeln ändern.  
  
 **Klasse**  
 Legt den Namen der Klasse, die das Objekt implementiert. Dieser Name basiert auf der Name, den Sie in **Kurznamen**, 'C', das Standard-Präfix für einen Klassennamen vorangestellt.  
  
 **.h-Datei**  
 Legt den Namen der Headerdatei für die neue Klasse des Objekts. Dieser Name basiert standardmäßig auf dem Namen, den Sie in bereitstellen **Kurznamen**. Klicken Sie auf die Schaltfläche, um den Dateinamen am Speicherort Ihrer Wahl speichern oder die Klassendeklaration an eine vorhandene Datei anfügen. Wenn Sie eine vorhandene Datei auswählen, der Assistent wird gespeichert, an den ausgewählten Speicherort bis auf **Fertig stellen**.  
  
 Der Assistent überschrieben eine Datei nicht. Wenn Sie den Namen einer vorhandenen Datei, auswählen, wenn Sie auf **Fertig stellen**, die vom Assistenten aufgefordert, anzugeben, ob die Klassendeklaration an den Inhalt der Datei angefügt werden sollen. Klicken Sie auf **Ja** anzufügenden Datei ein, klicken Sie auf **keine** zum Assistenten zurückzukehren und einen anderen Dateinamen angeben.  
  
 **CPP-Datei**  
 Legt den Namen der Implementierungsdatei für die neue Klasse des Objekts. Dieser Name basiert standardmäßig auf dem Namen, den Sie in bereitstellen **Kurznamen**. Klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um den Dateinamen am Speicherort Ihrer Wahl zu speichern. Die Datei wird nicht am ausgewählten Speicherort gespeichert, bis Sie auf **Fertig stellen** im Assistenten.  
  
 Der Assistent überschrieben eine Datei nicht. Wenn Sie den Namen einer vorhandenen Datei, auswählen, wenn Sie auf **Fertig stellen**, die vom Assistenten aufgefordert, anzugeben, ob die Implementierung der Klasse an den Inhalt der Datei angefügt werden sollen. Klicken Sie auf **Ja** anzufügenden Datei ein, klicken Sie auf **keine** zum Assistenten zurückzukehren und einen anderen Dateinamen angeben.  
  
 **Attributiert**  
 Gibt an, ob das Objekt Attribute verwendet. Wenn Sie einem attributierten ATL-Projekt ein Objekt hinzufügen, ist diese Option aktiviert und nicht verfügbar ist, ändern. Also können Sie nur attributierte Objekte zu einem Projekt mit Attribut-Unterstützung hinzufügen.  
  
 Sie können ein attributiertes Objekt nur ein ATL-Projekt hinzufügen, die Attribute verwendet. Wenn Sie diese Option für ein ATL-Projekt, die kein Attribut unterstützen verfügt auswählen, werden Sie vom Assistenten aufgefordert, anzugeben, ob Sie Attribut-Unterstützung zum Projekt hinzufügen möchten.  
  
 Standardmäßig werden alle Objekte, die Sie hinzufügen, nachdem Sie diese Option festlegen als attributierte festgelegt (das Kontrollkästchen ist aktiviert). Sie können dieses Kontrollkästchen, um ein Objekt hinzuzufügen, die Attribute nicht deaktivieren.  
  
 Finden Sie unter [Application Settings, ATL-Projekt-Assistent](../../atl/reference/application-settings-atl-project-wizard.md) und [grundlegende Funktionsweise von Attributen](../../windows/basic-mechanics-of-attributes.md) Weitere Informationen.  
  
### <a name="com"></a>COM  
 Enthält Informationen über die COM-Funktionalität für das Objekt.  
  
 **Co-Klasse**  
 Legt den Namen der Komponente-Klasse enthält eine Liste von Schnittstellen, die vom Objekt unterstützt wird.  
  
> [!NOTE]
>  Wenn Sie das Projekt unter Verwendung von Attributen erstellen oder auf dieser Seite des Assistenten angeben, dass das Steuerelement Attribute verwendet, können Sie diese Option nicht ändern, da ATL nicht enthalten ist die **Coclass** Attribut.  
  
 **Benutzeroberfläche**  
 Legt den Namen der Schnittstelle für das Objekt. Standardmäßig wird eine Schnittstelle namens "I" vorangestellt.  
  
 **Typ**  
 Legt die Beschreibung des Objekts, die in der Registrierung angezeigt wird  
  
 **Programm-ID**  
 Legt den Namen, den Container anstelle der CLSID des Objekts verwendet werden können. Dieses Feld wird nicht automatisch aufgefüllt. Wenn Sie dieses Feld nicht manuell auffüllen, kann das Steuerelement nicht mit anderen Tools verfügbar. Z. B. ActiveX-Steuerelemente, die generiert werden, ohne eine `ProgID` sind nicht verfügbar in der **ActiveX-Steuerelement einfügen** Dialogfeld. Weitere Informationen über das Dialogfeld finden Sie unter [ActiveX-Steuerelement-Dialogfeld einfügen](../../windows/insert-activex-control-dialog-box.md).  
  
## <a name="see-also"></a>Siehe auch  
 [ATL-Steuerelement](../../atl/reference/adding-an-atl-control.md)   
 [Hinzufügen von Funktionalität zum zusammengesetzten Steuerelement](../../atl/adding-functionality-to-the-composite-control.md)   
 [Grundlagen von ATL-COM-Objekten](../../atl/fundamentals-of-atl-com-objects.md)


