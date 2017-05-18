---
title: ATL COM+ 1.0-Assistenten | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.mts.overview
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding components
- ATL COM+ 1.0 Component Wizard
ms.assetid: 11670681-8671-4122-96a4-2e52f8dadce0
caps.latest.revision: 13
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 2729975c5e823965f4f5c16d5bfe317ce10a3670
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="atl-com-10-component-wizard"></a>ATL COM+ 1.0 Komponenten-Assistent
Verwenden Sie diesen Assistenten zum Hinzufügen eines Objekts zu Ihrem Projekt, das COM+ 1.0-Dienste, einschließlich Transaktionen unterstützt.  
  
 Sie können angeben, ob das Objekt duale Schnittstellen und die Automatisierung unterstützt. Sie können auch Unterstützung für die Schnittstelle Informationen, erweiterte Steuerelement, Transaktionen und asynchronen Message Queuing-angeben.  
  
## <a name="remarks"></a>Hinweise  
 Beginnend mit [!INCLUDE[vs_orcas_long](../../atl/reference/includes/vs_orcas_long_md.md)], die von diesem Assistenten erstellte Registrierungsskript registriert die COM-Komponenten unter **HKEY_CURRENT_USER** anstelle von **HKEY_LOCAL_MACHINE**. Um dieses Verhalten zu ändern, legen Sie die **Register-Komponente für alle Benutzer** Option des ATL-Assistenten.  
  
## <a name="names"></a>Namen  
 Geben Sie den Namen für das Objekt, die Schnittstelle und die Klassen, die dem Projekt hinzugefügt werden. Mit Ausnahme von **Kurznamen**, alle weiteren Felder unabhängig voneinander bearbeitet werden können. Wenn Sie den Text ändern **Kurznamen**, wirkt sich die Änderung auf die Namen in allen anderen Feldern auf dieser Seite. Wenn Sie ändern die **Co-Klasse** Name im COM-Abschnitt der Änderung wirkt sich die **Typ** und **ProgID** Dialogfelder, aber die **Schnittstelle** Name wird nicht geändert. Dieses Namenssystem ist so ausgelegt, dass alle Namen leicht identifizierbaren für Sie bei der Entwicklung Ihrer Kontrolle.  
  
 **Kurzname**  
 Legt den abgekürzten Namen für das Objekt. Der Name, der bestimmt die `Class` und `Coclass` Namen, die **cpp-Datei** und **.h-Datei** Namen, die **Schnittstelle** Namen, die **Typ** Namen, und die **ProgID**, sofern Sie diese Felder nicht einzeln ändern.  
  
 **.h-Datei**  
 Legt den Namen der Headerdatei für die neue Klasse des Objekts. Dieser Name basiert standardmäßig auf dem Namen, den Sie in bereitstellen **Kurznamen**. Klicken Sie auf die Schaltfläche, um den Dateinamen am Speicherort Ihrer Wahl speichern oder die Klassendeklaration an eine vorhandene Datei anfügen. Wenn Sie eine vorhandene Datei auswählen, der Assistent wird gespeichert, am ausgewählten Speicherort bis auf **Fertig stellen** im Assistenten.  
  
 Der Assistent überschrieben eine Datei nicht. Wenn Sie den Namen einer vorhandenen Datei, auswählen, wenn Sie auf **Fertig stellen**, die vom Assistenten aufgefordert, anzugeben, ob die Klassendeklaration an den Inhalt der Datei angefügt werden sollen. Klicken Sie auf **Ja** anzufügenden Datei ein, klicken Sie auf **keine** zum Assistenten zurückzukehren und einen anderen Dateinamen angeben.  
  
 **Klasse**  
 Legt den Namen der Klasse erstellt werden. Dieser Name basiert auf den Namen, den Sie in **Kurznamen**, 'C', das Standard-Präfix für einen Klassennamen vorangestellt.  
  
 **CPP-Datei**  
 Legt den Namen der Implementierungsdatei für die neue Klasse des Objekts. Dieser Name basiert standardmäßig auf den Namen, den Sie in **Kurznamen**. Klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um den Dateinamen am Speicherort Ihrer Wahl zu speichern. Die Datei wird nicht am ausgewählten Speicherort gespeichert, bis Sie auf **Fertig stellen** im Assistenten.  
  
 Der Assistent überschrieben eine Datei nicht. Wenn Sie den Namen einer vorhandenen Datei auswählen, wenn Sie auf **Fertig stellen**, die vom Assistenten aufgefordert, anzugeben, ob die Implementierung der Klasse an den Inhalt der Datei angefügt werden sollen. Klicken Sie auf **Ja** anzufügenden Datei ein, klicken Sie auf **keine** zum Assistenten zurückzukehren und einen anderen Dateinamen angeben.  
  
 **Attributiert**  
 Gibt an, ob das Objekt Attribute verwendet. Wenn Sie einem attributierten ATL-Projekt ein Objekt hinzufügen, ist diese Option aktiviert und nicht verfügbar ist, ändern. Also können Sie nur attributierte Objekte zu einem Projekt mit Attribut-Unterstützung hinzufügen.  
  
 Wenn Sie diese Option für ein ATL-Projekt, die kein Attribut unterstützen verfügt auswählen, werden Sie vom Assistenten aufgefordert, anzugeben, ob Sie Attribut-Unterstützung zum Projekt hinzufügen möchten.  
  
 Als attributiert konfiguriert (das Kontrollkästchen ist aktiviert), werden alle Objekte, die Sie hinzufügen, befolgen diese Einstellung festgelegt. Sie können dieses Kontrollkästchen, um ein Objekt hinzuzufügen, die Attribute nicht deaktivieren.  
  
 Finden Sie unter [Application Settings, ATL-Projekt-Assistent](../../atl/reference/application-settings-atl-project-wizard.md) und [grundlegende Funktionsweise von Attributen](../../windows/basic-mechanics-of-attributes.md) Weitere Informationen.  
  
### <a name="com"></a>COM  
 Enthält Informationen über die COM-Funktionalität für das Objekt.  
  
 **Co-Klasse**  
 Legt den Namen der Komponente-Klasse enthält eine Liste von Schnittstellen, die vom Objekt unterstützt wird.  
  
> [!NOTE]
>  Wenn Sie das Projekt unter Verwendung von Attributen erstellen oder auf dieser Seite des Assistenten angeben, dass die COM+ 1.0-Komponente Attribute verwendet, können Sie diese Option nicht ändern, da ATL nicht enthalten ist die `coclass` Attribut.  
  
 **Typ**  
 Legt die Beschreibung des Objekts, die in der Registrierung angezeigt wird  
  
 **Benutzeroberfläche**  
 Legt die Schnittstelle, die Sie für das Objekt zu erstellen. Diese Schnittstelle enthält die benutzerdefinierten Methoden.  
  
 **Programm-ID**  
 Legt den Namen, den Container anstelle der CLSID des Objekts verwendet werden können.  
  
## <a name="see-also"></a>Siehe auch  
 [ATL COM+ 1.0-Komponente](../../atl/reference/adding-an-atl-com-plus-1-0-component.md)


