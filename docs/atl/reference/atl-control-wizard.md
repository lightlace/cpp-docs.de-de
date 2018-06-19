---
title: ATL-Steuerelement-Assistent | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1df64cd0661a7f905ebcc068efb698306ac9007e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32363528"
---
# <a name="atl-control-wizard"></a>ATL-Steuerelement-Assistent
Fügt eine ATL-Projekt (oder einem MFC-Projekt mit ATL-Unterstützung) ein ATL-Steuerelement. Diesem Assistenten können eine der drei Arten von Steuerelementen einfügen:  
  
-   Standardkontrollblöcke  
  
-   Zusammengesetzte Steuerelemente  
  
-   DHTML-Steuerelemente  
  
 Darüber hinaus können Angabe ein nur minimale Kontrolle entfernen die Schnittstellen aus der [Schnittstellen](../../atl/reference/interfaces-atl-control-wizard.md) Liste, die als Standard für Steuerelemente, öffnen Sie in den meisten Container bereitgestellt werden. Sie können festlegen, dass die Schnittstellen, die für das Steuerelement in unterstützt werden sollen die **Schnittstellen** Seite des Assistenten.  
  
## <a name="remarks"></a>Hinweise  
 Von diesem Assistenten erstellte Registrierungsskript wird seine COM-Komponenten unter HKEY_CURRENT_USER statt HKEY_LOCAL_MACHINE registriert werden. Um dieses Verhalten zu ändern, legen Sie die **Register-Komponente für alle Benutzer** des ATL-Assistenten die Option.  
  
## <a name="names"></a>Namen  
 Geben Sie die Namen für das Objekt, Schnittstelle und Klassen, die dem Projekt hinzugefügt werden. Mit Ausnahme von **Kurzname**, alle anderen Felder können unabhängig voneinander geändert werden. Wenn Sie den Text für ändern **Kurzname**, in den Namen von allen anderen Feldern auf dieser Seite wird die Änderung übernommen. Wenn Sie ändern die **Co-Klasse** Verzeichnisnamens COM-Abschnitt, die Änderung wirkt sich die **Typ** Feld, aber die **Schnittstelle** Name und **ProgID** führen nicht ändern. Dieses naming Verhalten wurde entworfen, um alle Namen leicht erkennbaren für Sie bereitzustellen bei der Entwicklung Ihrer Kontrolle.  
  
> [!NOTE]
>  **Coclass** kann nur bei nicht attributierten Steuerelementen bearbeitet werden. Wenn Ihr Projekt attributiert, können nicht bearbeitet **Coclass**.  
  
### <a name="c"></a>C++  
 Enthält Informationen für die C++-Klasse erstellt, um das Objekt zu implementieren.  
  
 **Kurzname**  
 Legt den abgekürzten Namen für das Objekt. Der Namen, den Sie angeben, bestimmt die Klasse und **Coclass** benennt die Datei (. CPP und. H) Namen, den Schnittstellennamen und die **Typ** benennt, es sei denn, diese Felder einzeln zu ändern.  
  
 **Klasse**  
 Legt den Namen der Klasse, die das Objekt implementiert. Dieser Name wird auf Grundlage des Namens, die Sie gewähren **Kurzname**, "C", das Standard-Präfix für einen Klassennamen vorangestellt.  
  
 **.h-Datei**  
 Legt den Namen der Headerdatei für die neue Klasse des Objekts. Standardmäßig basiert auf den Namen, die Sie gewähren dieser Name **Kurzname**. Klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um den Dateinamen an den Speicherort Ihrer Wahl speichern oder die Klassendeklaration an eine vorhandene Datei anfügen. Wenn Sie eine vorhandene Datei auswählen, der Assistent wird nicht zum Speichern an den ausgewählten Speicherort bis auf **Fertig stellen**.  
  
 Der Assistent überschreibt eine Datei nicht. Wenn Sie den Namen einer vorhandenen Datei auswählen, wenn Sie auf **Fertig stellen**, werden vom Assistenten aufgefordert, um anzugeben, ob die Klassendeklaration an den Inhalt der Datei angefügt werden sollen. Klicken Sie auf **Ja** anzufügende Datei ein, klicken Sie auf **keine** zum Assistenten zurückzukehren, und geben Sie einen anderen Dateinamen an.  
  
 **CPP-Datei**  
 Legt den Namen der Implementierungsdatei für das neue Objekt-Klasse. Standardmäßig basiert auf den Namen, die Sie gewähren dieser Name **Kurzname**. Klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um den Dateinamen am Speicherort Ihrer Wahl zu speichern. Die Datei wird nicht an den ausgewählten Speicherort gespeichert, bis Sie auf **Fertig stellen** im Assistenten.  
  
 Der Assistent überschreibt eine Datei nicht. Wenn Sie den Namen einer vorhandenen Datei auswählen, wenn Sie auf **Fertig stellen**, werden vom Assistenten aufgefordert, um anzugeben, ob die Implementierung der Klasse mit dem Inhalt der Datei angefügt werden sollen. Klicken Sie auf **Ja** anzufügende Datei ein, klicken Sie auf **keine** zum Assistenten zurückzukehren, und geben Sie einen anderen Dateinamen an.  
  
 **Mit Attributen versehen**  
 Gibt an, ob das Objekt Attribute verwendet. Wenn Sie ein Objekt zu einem attributierten ATL-Projekt hinzufügen, ist diese Option ausgewählt und nicht verfügbar, um zu ändern. D. h. können Sie nur attributierte Objekte zu einem Projekt mit Attribut-Unterstützung hinzufügen.  
  
 Sie können ein attributiertes Objekt nur ein ATL-Projekt hinzufügen, die Attribute verwendet. Wenn Sie diese Option für eine ATL-Projekt, die über keinen Attribut unterstützen auswählen, werden Sie vom Assistenten aufgefordert, anzugeben, ob die Attribut-Unterstützung zum Projekt hinzufügen möchten.  
  
 Standardmäßig werden alle Objekte, die Sie hinzufügen, nachdem Sie diese Option festlegen als attributiert festgelegt (das Kontrollkästchen ist aktiviert). Sie können deaktivieren Sie dieses Kontrollkästchen, um ein Objekt hinzuzufügen, das keine Attribute verwendet.  
  
 Finden Sie unter [Anwendungseinstellungen, ATL-Projektassistenten](../../atl/reference/application-settings-atl-project-wizard.md) und [grundlegende Funktionsweise von Attributen](../../windows/basic-mechanics-of-attributes.md) für Weitere Informationen.  
  
### <a name="com"></a>COM  
 Enthält Informationen über die COM-Funktionalität für das Objekt.  
  
 **Co-Klasse**  
 Legt den Namen der Komponentenklasse, die eine Liste von Schnittstellen, die vom Objekt unterstützten enthält.  
  
> [!NOTE]
>  Wenn Sie das Projekt, das Verwenden von Attributen erstellen oder auf dieser Seite des Assistenten angeben, dass das Steuerelement Attribute verwendet, können Sie diese Option nicht ändern, da ATL nicht enthält die **Coclass** Attribut.  
  
 **Interface**  
 Legt den Namen der Schnittstelle für das Objekt fest. Standardmäßig wird ein Schnittstellenname mit "I" vorangestellt.  
  
 **Type**  
 Legt die Beschreibung des Objekts, die in der Registrierung angezeigt wird  
  
 **ProgID**  
 Legt den Namen, den Container, anstatt die CLSID des Objekts verwenden können. Dieses Feld wird nicht automatisch aufgefüllt. Wenn Sie dieses Feld nicht manuell aufzufüllen, möglicherweise das Steuerelement nicht für andere Tools verfügbar. Z. B. ActiveX-Steuerelemente, die generiert werden, ohne eine `ProgID` sind nicht verfügbar in der **ActiveX-Steuerelement einfügen** (Dialogfeld). Weitere Informationen zum Dialogfeld finden Sie unter [Einfügen von ActiveX-Steuerelement (Dialogfeld)](../../windows/insert-activex-control-dialog-box.md).  
  
## <a name="see-also"></a>Siehe auch  
 [ATL-Steuerelement](../../atl/reference/adding-an-atl-control.md)   
 [Hinzufügen von Funktionalität zu zusammengesetzten Steuerelementen](../../atl/adding-functionality-to-the-composite-control.md)   
 [Grundlagen von ARL COM-Objekten](../../atl/fundamentals-of-atl-com-objects.md)

