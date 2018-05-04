---
title: ATL-Eigenschaftenseiten-Assistent | Microsoft Docs
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
ms.openlocfilehash: 17c5d863ef14aeddcd66f813449b514360f657a4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="atl-property-page-wizard"></a>ATL-Eigenschaftenseiten-Assistent
Dieser Assistent [eines ATL-Projekts fügt eine Eigenschaftenseite](../../atl/reference/adding-an-atl-property-page.md) oder zu einem MFC-Projekt mit ATL-Unterstützung. Eine ATL-Eigenschaftenseite bietet eine Benutzeroberfläche zum Festlegen der Eigenschaften (oder die Methoden aufrufen) von einem oder mehreren COM-Objekten.  
  
## <a name="remarks"></a>Hinweise  
 Ab Visual Studio 2008 können von diesem Assistenten erstellte Registrierungsskript registriert die COM-Komponenten unter **HKEY_CURRENT_USER** anstelle von **HKEY_LOCAL_MACHINE**. Um dieses Verhalten zu ändern, legen Sie die **Register-Komponente für alle Benutzer** des ATL-Assistenten die Option.  
  
## <a name="names"></a>Namen  
 Geben Sie die Namen für das Objekt, Schnittstelle und Klassen, die dem Projekt hinzugefügt werden. Mit Ausnahme von **Kurzname**, alle anderen Felder können unabhängig voneinander bearbeitet werden. Wenn Sie den Text für ändern **Kurzname**, in den Namen von allen anderen Feldern auf dieser Seite wird die Änderung übernommen. Wenn Sie ändern die **Co-Klasse** Verzeichnisnamens COM-Abschnitt, die Änderung wirkt sich die **Typ** und **ProgID** Felder. Dieses naming Verhalten wurde entworfen, um alle Namen leicht erkennbaren für Sie bereitzustellen bei der Entwicklung die Eigenschaftenseite.  
  
> [!NOTE]
>  **Coclass** kann nur bei nicht attributierten Projekten bearbeitet werden. Wenn Ihr Projekt attributiert, können nicht bearbeitet **Coclass**.  
  
### <a name="c"></a>C++  
 Enthält Informationen für die C++-Klasse erstellt, um das Objekt zu implementieren.  
  
|||  
|-|-|  
|Begriff|Definition|  
|**Kurzname**|Legt den abgekürzten Namen für das Objekt. Der Namen, den Sie angeben, bestimmt die Klasse und **Co-Klasse** benennt die Datei (**cpp** und **h**) Namen, den **Typ** Namen und die  **ProgID**, es sei denn, diese Felder einzeln zu ändern.|  
|**.h-Datei**|Legt den Namen der Headerdatei für die neue Klasse des Objekts. Standardmäßig basiert auf den Namen, die Sie gewähren dieser Name **Kurzname**. Klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um den Dateinamen an den Speicherort Ihrer Wahl speichern oder die Klassendeklaration an eine vorhandene Datei anfügen. Wenn Sie eine vorhandene Datei auswählen, der Assistent wird nicht zum Speichern an den ausgewählten Speicherort bis auf **Fertig stellen** im Assistenten.<br /><br /> Der Assistent überschreibt eine Datei nicht. Wenn Sie den Namen einer vorhandenen Datei auswählen, wenn Sie auf **Fertig stellen**, werden vom Assistenten aufgefordert, um anzugeben, ob die Klassendeklaration an den Inhalt der Datei angefügt werden sollen. Klicken Sie auf **Ja** anzufügende Datei ein, klicken Sie auf **keine** zum Assistenten zurückzukehren, und geben Sie einen anderen Dateinamen an.|  
|**Klasse**|Legt den Namen der Klasse, die das Objekt implementiert. Dieser Name wird auf Grundlage des Namens, die Sie gewähren **Kurzname**, "C", das Standard-Präfix für einen Klassennamen vorangestellt.|  
|**CPP-Datei**|Legt den Namen der Implementierungsdatei für das neue Objekt-Klasse. Standardmäßig basiert auf den Namen, die Sie gewähren dieser Name **Kurzname**. Klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um den Dateinamen am Speicherort Ihrer Wahl zu speichern. Die Datei wird nicht an den ausgewählten Speicherort gespeichert, bis Sie auf **Fertig stellen** im Assistenten.<br /><br /> Der Assistent überschreibt eine Datei nicht. Wenn Sie den Namen einer vorhandenen Datei auswählen, wenn Sie auf **Fertig stellen**, werden vom Assistenten aufgefordert, um anzugeben, ob die Implementierung der Klasse mit dem Inhalt der Datei angefügt werden sollen. Klicken Sie auf **Ja** anzufügende Datei ein, klicken Sie auf **keine** zum Assistenten zurückzukehren, und geben Sie einen anderen Dateinamen an.|  
|**Mit Attributen versehen**|Gibt an, ob das Objekt Attribute verwendet. Wenn Sie ein Objekt zu einem attributierten ATL-Projekt hinzufügen, diese Option ausgewählt ist und so ändern Sie nicht verfügbar ist, d. h., Sie können hinzufügen nur attributiert Objekte mit Attribut-Unterstützung erstellten Testprojekt kein.<br /><br /> Sie können ein attributiertes Objekt nur ein ATL-Projekt hinzufügen, die Attribute verwendet. Wenn Sie diese Option für eine ATL-Projekt, die über keinen Attribut unterstützen auswählen, werden Sie vom Assistenten aufgefordert, anzugeben, ob die Attribut-Unterstützung zum Projekt hinzufügen möchten.<br /><br /> Standardmäßig werden alle Objekte, die Sie hinzufügen, nachdem Sie diese Option festlegen als attributiert festgelegt (das Kontrollkästchen ist aktiviert). Sie können deaktivieren Sie dieses Kontrollkästchen, um ein Objekt hinzuzufügen, das keine Attribute verwendet.<br /><br /> Finden Sie unter [Anwendungseinstellungen, ATL-Projektassistenten](../../atl/reference/application-settings-atl-project-wizard.md) und [grundlegende Funktionsweise von Attributen](../../windows/basic-mechanics-of-attributes.md) für Weitere Informationen.|  
  
### <a name="com"></a>COM  
 Enthält Informationen über die COM-Funktionalität für das Objekt.  
  
 **Co-Klasse**  
 Legt den Namen der Komponentenklasse, die eine Liste von Schnittstellen, die vom Objekt unterstützten enthält.  
  
> [!NOTE]
>  Wenn Sie das Projekt, das Verwenden von Attributen erstellen oder auf dieser Seite des Assistenten angeben, dass die Eigenschaftenseite Attribute verwendet, können Sie diese Option nicht ändern, da ATL nicht enthält die `coclass` Attribut.  
  
 **Type**  
 Legt die Beschreibung des Objekts, die in der Registrierung angezeigt wird  
  
 **ProgID**  
 Legt den Namen, den Container, anstatt die CLSID des Objekts verwenden können.  
  
## <a name="see-also"></a>Siehe auch  
 [Optionen, ATL-Eigenschaftenseiten-Assistent](../../atl/reference/options-atl-property-page-wizard.md)   
 [Zeichenfolgen, ATL-Eigenschaftenseiten-Assistent](../../atl/reference/strings-atl-property-page-wizard.md)   
 [Beispiel: Implementieren einer Eigenschaftenseite](../../atl/example-implementing-a-property-page.md)

