---
title: ATL-Eigenschaftenseiten-Assistent | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.ppg.overview
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding property pages
- ATL Property Page Wizard
ms.assetid: 6113e325-facd-4f68-b491-144d75209922
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 94bca969b150718450da166501abaea9c89b75d7
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43760382"
---
# <a name="atl-property-page-wizard"></a>ATL-Eigenschaftenseiten-Assistent

Dieser Assistent [ein ATL-Projekt auf einer Eigenschaftenseite fügt](../../atl/reference/adding-an-atl-property-page.md) oder zu einem MFC-Projekt mit ATL-Unterstützung. Eine ATL-Eigenschaftenseite bietet eine Benutzeroberfläche zum Festlegen der Eigenschaften (oder Aufrufen der Methoden) von ein oder mehrere COM-Objekten.

## <a name="remarks"></a>Hinweise

Ab Visual Studio 2008 wird von diesem Assistenten erstellte Registrierungsskript seine COM-Komponenten unter registriert **HKEY_CURRENT_USER** anstelle von **HKEY_LOCAL_MACHINE**. Um dieses Verhalten zu ändern, legen Sie die **registerkomponenten für alle Benutzer** des ATL-Assistenten die Option.

## <a name="names"></a>Namen

Geben Sie die Namen für das Objekt, die Schnittstelle und die Klassen, die dem Projekt hinzugefügt werden. Mit Ausnahme von **Kurznamen**, alle anderen Felder können unabhängig voneinander bearbeitet werden. Wenn Sie den Text für ändern **Kurznamen**, in den Namen von allen anderen Feldern auf dieser Seite wird die Änderung übernommen. Wenn Sie ändern die **Co-Klasse** Name in der COM-Abschnitt die Änderung wirkt sich die **Typ** und **ProgID** Felder. Diese Namenssystem ist so ausgelegt, alle Namen leicht identifizierbaren für Sie, wie Sie Ihr Eigenschaftenseite entwickeln.

> [!NOTE]
>  **Co-Klasse** kann nur nicht attributierte Projekten bearbeitet werden. Wenn Ihr Projekt zugeordnet sind, können nicht bearbeitet **Co-Klasse**.

### <a name="c"></a>C++

Enthält Informationen für die C++-Klasse erstellt, um das Objekt implementiert.

|||
|-|-|
|Begriff|Definition|
|**Kurzname**|Legt den abgekürzten Namen für das Objekt fest. Der Name, den Sie angeben, bestimmt die Klasse und **Co-Klasse** -Namen ist, wird die Datei (**cpp** und **h**) Namen, die **Typ** Namen und die  **ProgID**, es sei denn, Sie diese Felder einzeln ändern.|
|**H-Datei**|Legt den Namen der Headerdatei für die neue Klasse des Objekts fest. Standardmäßig basiert auf den Namen, den Sie, in bereitstellen diesen Namen **Kurznamen**. Klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um den Dateinamen am gewünschten Speicherort zu speichern oder um die Klassendeklaration an eine vorhandene Datei anzufügen. Wenn Sie eine vorhandene Datei auswählen, der Assistent wird speichern Sie es nicht in den ausgewählten Speicherort bis auf **Fertig stellen** im Assistenten.<br /><br /> Der Assistent überschreibt Dateien nicht. Wenn Sie den Namen einer vorhandenen Datei auswählen, fordert der Assistent Sie dazu auf, anzugeben, ob die Klassendeklaration an die Inhalte der Datei angefügt werden sollen, wenn Sie auf **Fertig stellen** klicken. Klicken Sie auf **Ja**, um die Datei anzufügen. Klicken Sie auf **Nein**, um zum Assistenten zurückzukehren und einen anderen Dateinamen anzugeben.|
|**Klasse**|Legt den Namen der Klasse, die das Objekt implementiert. Dieser Name basiert auf den Namen, den Sie in bereitstellen **Kurznamen**ist 'C', das typische Präfix für einen Klassennamen vorangestellt.|
|**CPP-Datei**|Legt den Namen der Implementierungsdatei für die neue Klasse des Objekts fest. Standardmäßig basiert auf den Namen, den Sie, in bereitstellen diesen Namen **Kurznamen**. Klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um den Dateinamen am gewünschten Speicherort zu speichern. Die Datei wird nicht am ausgewählten Speicherort gespeichert, bis Sie im Assistenten auf **Fertig stellen** klicken.<br /><br /> Der Assistent überschreibt Dateien nicht. Wenn Sie den Namen einer vorhandenen Datei auswählen, fordert der Assistent Sie dazu auf, anzugeben, ob die Klassenimplementierung an die Inhalte der Datei angefügt werden sollen, wenn Sie auf **Fertig stellen** klicken. Klicken Sie auf **Ja**, um die Datei anzufügen. Klicken Sie auf **Nein**, um zum Assistenten zurückzukehren und einen anderen Dateinamen anzugeben.|
|**Zugeordnet sind**|Gibt an, ob das Objekt Attribute verwendet. Wenn Sie ein Objekt eine attributierten ATL-Projekt hinzufügen, diese Option ausgewählt ist, und so ändern Sie nicht verfügbar ist, d. h. Sie hinzufügen können, nur Objekte mit Attribut-Unterstützung erstellten Projekt zugeordnet.<br /><br /> Sie können ein attributiertes Objekt nur ein ATL-Projekt hinzufügen, die Attribute verwendet. Wenn Sie diese Option für ein ATL-Projekt, die nicht unterstützen Attribut verfügt auswählen, fordert der Assistent Sie angeben, ob die Attribut-Unterstützung zum Projekt hinzufügen möchten.<br /><br /> Standardmäßig werden alle Objekte, die Sie hinzufügen, nachdem Sie diese Option festlegen als attributierten festgelegt (das Kontrollkästchen ist aktiviert). Sie können festlegen, löschen Sie dieses Kontrollkästchen, um ein Objekt hinzuzufügen, die keine Attribute verwendet.<br /><br /> Finden Sie unter [Anwendungseinstellungen, ATL-Projektassistenten](../../atl/reference/application-settings-atl-project-wizard.md) und [grundlegende Funktionsweise von Attributen](../../windows/basic-mechanics-of-attributes.md) für Weitere Informationen.|

### <a name="com"></a>COM

Enthält Informationen über die COM-Funktionalität für das Objekt.

**Co-Klasse**  
Legt den Namen der Komponentenklasse, die eine Liste der Schnittstellen, die vom Objekt unterstützten enthält.

> [!NOTE]
>  Wenn Sie das Projekt mithilfe von Attributen erstellen, oder auf dieser Seite des Assistenten angeben, dass auf der Seite der Attribute verwendet, können Sie diese Option nicht ändern, da ATL nicht enthalten ist das `coclass` Attribut.

**Type**  
Legt die Beschreibung des Objekts, die in der Registrierung angezeigt wird

**ProgID**  
Legt den Namen, den Container anstatt der CLSID des Objekts verwenden können.

## <a name="see-also"></a>Siehe auch

[Optionen, ATL-Eigenschaftenseiten-Assistent](../../atl/reference/options-atl-property-page-wizard.md)   
[Zeichenfolgen, ATL-Eigenschaftenseiten-Assistent](../../atl/reference/strings-atl-property-page-wizard.md)   
[Beispiel: Implementieren einer Eigenschaftenseite](../../atl/example-implementing-a-property-page.md)

