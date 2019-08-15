---
title: Csnapinpropertypageimpl-Klasse
ms.date: 11/04/2016
f1_keywords:
- CSnapInPropertyPageImpl
- ATLSNAP/ATL::CSnapInPropertyPageImpl
- ATLSNAP/ATL::CSnapInPropertyPageImpl::CSnapInPropertyPageImpl
- ATLSNAP/ATL::CSnapInPropertyPageImpl::CancelToClose
- ATLSNAP/ATL::CSnapInPropertyPageImpl::Create
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnApply
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnHelp
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnKillActive
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnQueryCancel
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnReset
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnSetActive
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnWizardBack
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnWizardFinish
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnWizardNext
- ATLSNAP/ATL::CSnapInPropertyPageImpl::QuerySiblings
- ATLSNAP/ATL::CSnapInPropertyPageImpl::SetModified
- ATLSNAP/ATL::CSnapInPropertyPageImpl::m_psp
helpviewer_keywords:
- snap-ins, property pages
- snap-ins
- property pages, ATL
- CSnapInPropertyPageImpl class
ms.assetid: 75bdce5a-985e-4166-bd44-493132e023c4
ms.openlocfilehash: abf4cf5804f6ef7335192feb298f1a4a06f841e4
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69496398"
---
# <a name="csnapinpropertypageimpl-class"></a>Csnapinpropertypageimpl-Klasse

Diese Klasse stellt Methoden zum Implementieren eines Snap-in-Eigenschaften Seiten Objekts bereit.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

## <a name="syntax"></a>Syntax

```
CSnapInPropertyPageImpl : public CDialogImplBase
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CSnapInPropertyPageImpl::CSnapInPropertyPageImpl](#csnapinpropertypageimpl)|Konstruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CSnapInPropertyPageImpl::CancelToClose](#canceltoclose)|Ändert den Status der Schaltflächen **OK** und **Abbrechen** .|
|[CSnapInPropertyPageImpl::Create](#create)|Initialisiert ein neu erstelltes `CSnapInPropertyPageImpl` -Objekt.|
|[CSnapInPropertyPageImpl::OnApply](#onapply)|Wird von Framework aufgerufen, wenn der Benutzer auf die Schaltfläche **jetzt** übernehmen klickt, während ein Eigenschaften Blatt des Assistenten angezeigt wird.|
|[CSnapInPropertyPageImpl::OnHelp](#onhelp)|Wird von Framework aufgerufen, wenn der Benutzer auf die Schaltfläche " **Hilfe** " klickt, während er ein Eigenschaften Blatt des Assistenten Typs verwendet.|
|[CSnapInPropertyPageImpl::OnKillActive](#onkillactive)|Wird von Framework aufgerufen, wenn die aktuelle Seite nicht mehr aktiv ist.|
|[CSnapInPropertyPageImpl::OnQueryCancel](#onquerycancel)|Wird von Framework aufgerufen, wenn der Benutzer auf die Schaltfläche **Abbrechen** klickt und bevor der Abbruch stattfindet.|
|[CSnapInPropertyPageImpl::OnReset](#onreset)|Wird von Framework aufgerufen, wenn der Benutzer auf die Schaltfläche **Zurücksetzen** klickt, während ein Eigenschaften Blatt des Assistenten angezeigt wird.|
|[CSnapInPropertyPageImpl::OnSetActive](#onsetactive)|Wird von Framework aufgerufen, wenn die aktuelle Seite aktiv wird.|
|[CSnapInPropertyPageImpl::OnWizardBack](#onwizardback)|Wird von Framework aufgerufen, wenn der Benutzer auf die Schaltfläche " **zurück** " klickt, während er ein Eigenschaften Blatt des Assistenten Typs verwendet.|
|[CSnapInPropertyPageImpl::OnWizardFinish](#onwizardfinish)|Wird von Framework aufgerufen, wenn der Benutzer auf die Schaltfläche **Fertig** stellen klickt, während ein Eigenschaften Blatt des Assistenten angezeigt wird.|
|[CSnapInPropertyPageImpl::OnWizardNext](#onwizardnext)|Wird von Framework aufgerufen, wenn der Benutzer auf die Schaltfläche " **weiter** " klickt, während er ein Eigenschaften Blatt des Assistenten Typs verwendet.|
|[CSnapInPropertyPageImpl::QuerySiblings](#querysiblings)|Leitet die aktuelle Nachricht an alle Seiten des Eigenschaften Blatts weiter.|
|[CSnapInPropertyPageImpl::SetModified](#setmodified)|Ruft auf, um die Schaltfläche **jetzt anwenden** zu aktivieren oder zu deaktivieren.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CSnapInPropertyPageImpl::m_psp](#m_psp)|`PROPSHEETPAGE` Die`CSnapInPropertyPageImpl` vom-Objekt verwendete Windows-Struktur.|

## <a name="remarks"></a>Hinweise

`CSnapInPropertyPageImpl`stellt eine grundlegende Implementierung für ein Snap-in-Eigenschaften Seiten Objekt bereit. Die grundlegenden Features einer Snap-in-Eigenschaften Seite werden mithilfe verschiedener Schnittstellen und Kartentypen implementiert.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CDialogImplBase`

`CSnapInPropertyPageImpl`

## <a name="requirements"></a>Anforderungen

**Header:** atlsnap. h

##  <a name="canceltoclose"></a>Csnapinpropertypageimpl:: canceldeclose

Diese Funktion wird aufgerufen, nachdem eine nicht BEHEB Bare Änderung an den Daten auf einer Seite eines modalen Eigenschaften Blatts vorgenommen wurde.

```
void CancelToClose();
```

### <a name="remarks"></a>Hinweise

Diese Funktion ändert die Schaltfläche **OK** , um die Schaltfläche **Abbrechen** zu **Schließen** und zu deaktivieren. Diese Änderung warnt den Benutzer, dass eine Änderung permanent ist und die Änderungen nicht abgebrochen werden können.

Die `CancelToClose` Member-Funktion führt in einem nicht modalem Eigenschaften Blatt keine Aktion aus, da ein nicht modalem Eigenschaften Blatt standardmäßig nicht über die Schaltfläche **Abbrechen** verfügt.

##  <a name="csnapinpropertypageimpl"></a>Csnapinpropertypageimpl:: csnapinpropertypageimpl

Erstellt ein `CSnapInPropertyPageImpl`-Objekt.

```
CSnapInPropertyPageImpl(LPCTSTR lpszTitle = NULL);
```

### <a name="parameters"></a>Parameter

*lpszTitle*<br/>
in Der Titel der Eigenschaften Seite.

### <a name="remarks"></a>Hinweise

Um die zugrunde liegende Struktur zu initialisieren, rufen Sie [csnapinpropertypageimpl:: Create](#create)auf.

##  <a name="create"></a>Csnapinpropertypageimpl:: Create

Mit dieser Funktion können Sie die zugrunde liegende Struktur der Eigenschaften Seite initialisieren.

```
HPROPSHEETPAGE Create();
```

### <a name="return-value"></a>Rückgabewert

Ein Handle für eine `PROPSHEETPAGE` -Struktur, die die Attribute des neu erstellten Eigenschaften Blatts enthält.

### <a name="remarks"></a>Hinweise

Sie sollten zuerst [csnapinpropertypageimpl:: csnapinpropertypageimpl](#csnapinpropertypageimpl) aufrufen, bevor Sie diese Funktion aufrufen.

##  <a name="m_psp"></a>Csnapinpropertypageimpl:: m_psp

`m_psp`ist eine-Struktur, deren Member die Merkmale `PROPSHEETPAGE`von speichern.

```
PROPSHEETPAGE m_psp;
```

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Struktur, um die Darstellung einer Eigenschaften Seite zu initialisieren, nachdem Sie erstellt wurde.

Weitere Informationen zu dieser Struktur, einschließlich einer Auflistung ihrer Member, finden Sie unter [PROPSHEETPAGE](/windows/win32/api/prsht/ns-prsht-propsheetpagea_v3) in der Windows SDK.

##  <a name="onapply"></a>Csnapinpropertypageimpl:: OnApply

Diese Member-Funktion wird aufgerufen, wenn der Benutzer auf die Schaltfläche " **OK** " oder " **jetzt anwenden** " klickt.

```
BOOL OnApply();
```

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die Änderungen akzeptiert werden. andernfalls 0.

### <a name="remarks"></a>Hinweise

Bevor `OnApply` vom Framework aufgerufen werden kann, müssen Sie aufgerufen `SetModified` haben und den-Parameter auf true festgelegt haben. Dadurch wird die Schaltfläche **jetzt anwenden** aktiviert, sobald der Benutzer eine Änderung auf der Eigenschaften Seite vornimmt.

Überschreiben Sie diese Member-Funktion, um anzugeben, welche Aktion das Programm durchführt, wenn der Benutzer auf die Schaltfläche **jetzt anwenden** klickt Beim Überschreiben sollte die Funktion true zurückgeben, um Änderungen zu akzeptieren, und false, um zu verhindern, dass Änderungen wirksam werden.

Die Standard Implementierung von `OnApply` gibt true zurück.

##  <a name="onhelp"></a>Csnapinpropertypageimpl:: onhelp

Diese Member-Funktion wird aufgerufen, wenn der Benutzer auf die **Hilfe** Schaltfläche für die Eigenschaften Seite klickt.

```
void OnHelp();
```

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Member-Funktion, um die Hilfe für die Eigenschaften Seite anzuzeigen.

##  <a name="onkillactive"></a>Csnapinpropertypageimpl:: OnKillActive

Diese Member-Funktion wird aufgerufen, wenn die Seite nicht mehr die aktive Seite ist.

```
BOOL OnKillActive();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Daten erfolgreich aktualisiert wurden. andernfalls 0.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Member-Funktion, um spezielle Daten Validierungs Tasks auszuführen.

##  <a name="onquerycancel"></a>Csnapinpropertypageimpl:: OnQueryCancel

Diese Member-Funktion wird aufgerufen, wenn der Benutzer auf die Schaltfläche **Abbrechen** klickt und bevor die Aktion abbrechen stattfindet.

```
BOOL OnQueryCancel();
```

### <a name="return-value"></a>Rückgabewert

Nicht NULL, um den Abbruch Vorgang zuzulassen. andernfalls 0.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Member-Funktion, um eine Aktion anzugeben, die das Programm annimmt, wenn der Benutzer auf die Schaltfläche **Abbrechen** klickt

Die Standard Implementierung von `OnQueryCancel` gibt true zurück.

##  <a name="onreset"></a>Csnapinpropertypageimpl:: onreset

Diese Member-Funktion wird aufgerufen, wenn der Benutzer auf die Schaltfläche **Abbrechen** klickt.

```
void OnReset();
```

### <a name="remarks"></a>Hinweise

Wenn diese Funktion aufgerufen wird, werden Änderungen an allen Eigenschaften Seiten, die zuvor durch den Benutzer durch Klicken auf die Schaltfläche **jetzt anwenden** vorgenommen wurden, verworfen, und das Eigenschaften Blatt behält den Fokus.

Überschreiben Sie diese Element Funktion, um anzugeben, welche Aktion das Programm durchführt, wenn der Benutzer auf die Schaltfläche **Abbrechen** klickt.

##  <a name="onsetactive"></a>Csnapinpropertypageimpl:: OnSetActive

Diese Member-Funktion wird aufgerufen, wenn die Seite vom Benutzer ausgewählt und zur aktiven Seite wird.

```
BOOL OnSetActive();
```

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die Seite erfolgreich festgelegt wurde. andernfalls 0.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Member-Funktion, um Aufgaben auszuführen, wenn eine Seite aktiviert wird. Die außer Kraft setzung dieser Member-Funktion sollte die Standardversion aufzurufen, bevor eine andere Verarbeitung erfolgt.

Die Standard Implementierung gibt true zurück.

##  <a name="onwizardback"></a>Csnapinpropertypageimpl:: onwizardback

Diese Member-Funktion wird aufgerufen, wenn der Benutzer in einem Assistenten auf die Schaltfläche " **zurück** " klickt.

```
BOOL OnWizardBack();
```

### <a name="return-value"></a>Rückgabewert

- 0, um automatisch mit der vorherigen Seite fortzufahren.

- -1, um zu verhindern, dass die Seite geändert wird.

Um zu einer anderen Seite als der nächsten zu springen, geben Sie den Bezeichner des Dialog Felds zurück, das angezeigt werden soll.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Member-Funktion, um eine Aktion anzugeben, die der Benutzer beim Klicken auf die Schaltfläche **zurück** ausführen muss.

##  <a name="onwizardfinish"></a>Csnapinpropertypageimpl:: onwizardfinish

Diese Member-Funktion wird aufgerufen, wenn der Benutzer auf die Schaltfläche **Fertig** stellen in einem Assistenten klickt.

```
BOOL OnWizardFinish();
```

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn das Eigenschaften Blatt gelöscht wird, wenn der Assistent abgeschlossen ist. andernfalls NULL.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Member-Funktion, um eine Aktion anzugeben, die der Benutzer beim Klicken auf die Schaltfläche **Fertig** stellen ausführen muss.

##  <a name="onwizardnext"></a>Csnapinpropertypageimpl:: onwizardnext

Diese Member-Funktion wird aufgerufen, wenn der Benutzer in einem Assistenten auf die Schaltfläche **weiter** klickt.

```
BOOL OnWizardNext();
```

### <a name="return-value"></a>Rückgabewert

- 0, um automatisch mit der nächsten Seite fortzufahren.

- -1, um zu verhindern, dass die Seite geändert wird.

Um zu einer anderen Seite als der nächsten zu springen, geben Sie den Bezeichner des Dialog Felds zurück, das angezeigt werden soll.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Member-Funktion, um eine Aktion anzugeben, die der Benutzer beim Klicken auf die Schaltfläche **weiter** ausführen muss.

##  <a name="querysiblings"></a>Csnapinpropertypageimpl:: querysiblings

Diese Member-Funktion wird aufgerufen, um eine Meldung an jede Seite im Eigenschaften Blatt weiterzuleiten.

```
LRESULT QuerySiblings(WPARAM wParam, LPARAM lParam);
```

### <a name="parameters"></a>Parameter

*wParam*<br/>
in Gibt zusätzliche Nachrichten abhängige Informationen an.

*lParam*<br/>
in Gibt zusätzliche Nachrichten abhängige Informationen an.

### <a name="return-value"></a>Rückgabewert

Ein Wert ungleich 0 (null), wenn die Meldung nicht an die nächste Eigenschaften Seite weitergeleitet werden soll. andernfalls NULL.

### <a name="remarks"></a>Hinweise

Wenn eine Seite einen Wert ungleich 0 (null) zurückgibt, sendet das Eigenschaften Blatt die Nachricht nicht an nachfolgende Seiten.

##  <a name="setmodified"></a>Csnapinpropertypageimpl:: SetModified

Diese Member-Funktion wird aufgerufen, um die Schaltfläche " **jetzt anwenden** " zu aktivieren oder zu deaktivieren, je nachdem, ob die Einstellungen auf der Eigenschaften Seite auf das entsprechende externe Objekt angewendet werden sollen.

```
void SetModified(BOOL bChanged = TRUE);
```

### <a name="parameters"></a>Parameter

*bchanged*<br/>
in TRUE, um anzugeben, dass die Einstellungen der Eigenschaften Seite seit der letzten Anwendung geändert wurden. FALSE, um anzugeben, dass die Eigenschaften Seiteneinstellungen angewendet wurden, oder sollte ignoriert werden.

### <a name="remarks"></a>Hinweise

Das Eigenschaften Blatt verfolgt, welche Seiten geändert werden, d. h. Eigenschaften Seiten, für die Sie aufgerufen `SetModified( TRUE )`haben. Die Schaltfläche **jetzt anwenden** wird immer aktiviert, wenn Sie `SetModified( TRUE )` für eine der Seiten aufzurufen. Die Schaltfläche **jetzt anwenden** wird deaktiviert, wenn Sie `SetModified( FALSE )` für eine der Seiten aufzurufen, aber nur, wenn keine der anderen Seiten "Dirty" ist.

## <a name="see-also"></a>Siehe auch

[Klassen Übersicht](../../atl/atl-class-overview.md)
