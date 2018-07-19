---
title: CSnapInPropertyPageImpl-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- snap-ins, property pages
- snap-ins
- property pages, ATL
- CSnapInPropertyPageImpl class
ms.assetid: 75bdce5a-985e-4166-bd44-493132e023c4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 56a57d3fe0eb1a016af9eee8539cd7f57a12ddf5
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37880559"
---
# <a name="csnapinpropertypageimpl-class"></a>CSnapInPropertyPageImpl-Klasse
Diese Klasse stellt Methoden zum Implementieren einer Snap-in-Eigenschaft-Page-Objekt.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.  
  
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
|[CSnapInPropertyPageImpl::CancelToClose](#canceltoclose)|Ändert den Status der **OK** und **Abbrechen** Schaltflächen.|  
|[CSnapInPropertyPageImpl::Create](#create)|Initialisiert eine neu erstellte `CSnapInPropertyPageImpl` Objekt.|  
|[CSnapInPropertyPageImpl::OnApply](#onapply)|Vom Framework aufgerufen, wenn der Benutzer klickt auf die **jetzt übernehmen** Schaltfläche während einer Benutzens eines assistentartigen Eigenschaftsblatts.|  
|[CSnapInPropertyPageImpl::OnHelp](#onhelp)|Vom Framework aufgerufen, wenn der Benutzer klickt auf die **Hilfe** Schaltfläche während einer Benutzens eines assistentartigen Eigenschaftsblatts.|  
|[CSnapInPropertyPageImpl::OnKillActive](#onkillactive)|Vom Framework aufgerufen, wenn die aktuelle Seite nicht mehr aktiv ist.|  
|[CSnapInPropertyPageImpl::OnQueryCancel](#onquerycancel)|Vom Framework aufgerufen, wenn der Benutzer klickt auf die **Abbrechen** Schaltfläche und bevor der Abbruchvorgang stattgefunden hat.|  
|[CSnapInPropertyPageImpl::OnReset](#onreset)|Vom Framework aufgerufen, wenn der Benutzer klickt auf die **zurücksetzen** Schaltfläche während einer Benutzens eines assistentartigen Eigenschaftsblatts.|  
|[CSnapInPropertyPageImpl::OnSetActive](#onsetactive)|Vom Framework aufgerufen, wenn die aktuelle Seite aktiv ist.|  
|[CSnapInPropertyPageImpl::OnWizardBack](#onwizardback)|Vom Framework aufgerufen, wenn der Benutzer klickt auf die **wieder** Schaltfläche während einer Benutzens eines assistentartigen Eigenschaftsblatts.|  
|[CSnapInPropertyPageImpl::OnWizardFinish](#onwizardfinish)|Vom Framework aufgerufen, wenn der Benutzer klickt auf die **Fertig stellen** Schaltfläche während einer Benutzens eines assistentartigen Eigenschaftsblatts.|  
|[CSnapInPropertyPageImpl::OnWizardNext](#onwizardnext)|Vom Framework aufgerufen, wenn der Benutzer klickt auf die **Weiter** Schaltfläche während einer Benutzens eines assistentartigen Eigenschaftsblatts.|  
|[CSnapInPropertyPageImpl::QuerySiblings](#querysiblings)|Leitet die aktuelle Meldung für alle Seiten des Eigenschaftenblatts an.|  
|[CSnapInPropertyPageImpl::SetModified](#setmodified)|Aufruf zum Aktivieren oder Deaktivieren der **jetzt übernehmen** Schaltfläche.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSnapInPropertyPageImpl::m_psp](#m_psp)|Die Windows `PROPSHEETPAGE` Struktur, die verwendet werden, indem die `CSnapInPropertyPageImpl` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 `CSnapInPropertyPageImpl` Stellt eine grundlegende Implementierung für eine Seitenobjekt-Snap-in-Eigenschaft. Die grundlegenden Funktionen einer Eigenschaftenseite-Snap-in werden mithilfe von mehrere Schnittstellen implementiert und Zuordnungstypen.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CDialogImplBase`  
  
 `CSnapInPropertyPageImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlsnap.h  
  
##  <a name="canceltoclose"></a>  CSnapInPropertyPageImpl::CancelToClose  
 Rufen Sie diese Funktion aus, nachdem auf die Daten auf einer Datenseite ein modales Eigenschaftsblatt eine nicht behebbare Änderung vorgenommen wurde.  
  
```
void CancelToClose();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ändert sich die **OK** Schaltfläche **schließen** und Deaktivieren der **Abbrechen** Schaltfläche. Dies ändern, Warnungen, die der Benutzer, dass eine Änderung Permanent und die Änderungen werden nicht abgebrochen werden kann.  
  
 Die `CancelToClose` Memberfunktion ist "nothing" in einem nicht modalen Eigenschaftenblatts, da kein nicht modalen Eigenschaftenblatts verfügt eine **Abbrechen** Schaltfläche in der Standardeinstellung.  
  
##  <a name="csnapinpropertypageimpl"></a>  CSnapInPropertyPageImpl::CSnapInPropertyPageImpl  
 Erstellt ein `CSnapInPropertyPageImpl`-Objekt.  
  
```
CSnapInPropertyPageImpl(LPCTSTR lpszTitle = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszTitle*  
 [in] Der Titel der Eigenschaftenseite.  
  
### <a name="remarks"></a>Hinweise  
 Um die zugrunde liegende Struktur zu initialisieren, rufen Sie [CSnapInPropertyPageImpl::Create](#create).  
  
##  <a name="create"></a>  CSnapInPropertyPageImpl::Create  
 Rufen Sie diese Funktion, um die zugrunde liegende Struktur der Seite zu initialisieren.  
  
```
HPROPSHEETPAGE Create();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für ein `PROPSHEETPAGE` Struktur, die die Attribute des neu erstellten Eigenschaftenblatt enthält.  
  
### <a name="remarks"></a>Hinweise  
 Sie sollten zuerst Aufrufen [CSnapInPropertyPageImpl::CSnapInPropertyPageImpl](#csnapinpropertypageimpl) vor dem Aufrufen dieser Funktion.  
  
##  <a name="m_psp"></a>  CSnapInPropertyPageImpl::m_psp  
 `m_psp` ist eine Struktur, deren Mitglieder, die Merkmale des speichern `PROPSHEETPAGE`.  
  
```
PROPSHEETPAGE m_psp;
```  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Struktur, um die Darstellung einer Eigenschaftenseite zu initialisieren, sobald es erstellt wurde.  
  
 Weitere Informationen zu dieser Struktur, einschließlich einer Liste der Member, finden Sie unter [PROPSHEETPAGE](http://msdn.microsoft.com/library/aa815151) im Windows SDK.  
  
##  <a name="onapply"></a>  CSnapInPropertyPageImpl::OnApply  
 Diese Memberfunktion wird immer dann aufgerufen, wenn der Benutzer klickt auf die **OK** oder **jetzt übernehmen** Schaltfläche.  
  
```
BOOL OnApply();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Änderungen akzeptiert werden; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Vor dem `OnApply` kann aufgerufen werden, durch das Framework Sie aufgerufen hat, `SetModified` und als Parameter auf "true" festgelegt. Dies aktiviert die **jetzt übernehmen** Schaltfläche, sobald der Benutzer eine Änderung auf der Eigenschaftenseite vornimmt.  
  
 Überschreiben Sie diese Memberfunktion zum angeben, welche Aktion das Programm akzeptiert, klickt der Benutzer die **jetzt übernehmen** Schaltfläche. Wenn Sie überschreiben, sollte die Funktion "true", um Änderungen zu übernehmen und "false", um zu verhindern, dass die Änderungen wirksam zurück.  
  
 Die standardmäßige Implementierung des `OnApply` gibt TRUE zurück.  
  
##  <a name="onhelp"></a>  CSnapInPropertyPageImpl::OnHelp  
 Diese Memberfunktion wird immer dann aufgerufen, wenn der Benutzer klickt auf die **Hilfe** Schaltfläche für die Eigenschaftenseite.  
  
```
void OnHelp();
```  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Memberfunktion zum Anzeigen der Hilfe für die Eigenschaftenseite.  
  
##  <a name="onkillactive"></a>  CSnapInPropertyPageImpl::OnKillActive  
 Diese Memberfunktion wird aufgerufen, wenn die Seite nicht mehr zur aktiven Seite wird.  
  
```
BOOL OnKillActive();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn Daten wurde erfolgreich aktualisiert wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Memberfunktion zum Durchführen von Aufgaben für spezielle-Überprüfung.  
  
##  <a name="onquerycancel"></a>  CSnapInPropertyPageImpl::OnQueryCancel  
 Diese Memberfunktion wird immer dann aufgerufen, wenn der Benutzer klickt auf die **Abbrechen** Schaltfläche, und bevor der Abbruchvorgang Aktion stattgefunden hat.  
  
```
BOOL OnQueryCancel();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null den Vorgang abbrechen können; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Memberfunktion, um eine Aktion angeben, das Programm akzeptiert, klickt der Benutzer, die **Abbrechen** Schaltfläche.  
  
 Die standardmäßige Implementierung des `OnQueryCancel` gibt TRUE zurück.  
  
##  <a name="onreset"></a>  CSnapInPropertyPageImpl::OnReset  
 Diese Memberfunktion wird immer dann aufgerufen, wenn der Benutzer klickt auf die **Abbrechen** Schaltfläche.  
  
```
void OnReset();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn diese Funktion aufgerufen wird, ändert sich für alle Eigenschaftenseiten, die durch den Benutzer, die Sie zuvor auf vorgenommen wurden die **jetzt übernehmen** Schaltfläche werden verworfen, und das Eigenschaftenblatt behält den Fokus.  
  
 Überschreiben Sie diese Memberfunktion zum angeben, welche Aktion das Programm akzeptiert, klickt der Benutzer die **Abbrechen** Schaltfläche.  
  
##  <a name="onsetactive"></a>  CSnapInPropertyPageImpl::OnSetActive  
 Diese Memberfunktion wird immer dann aufgerufen, wenn die Seite vom Benutzer ausgewählt wird und wird zur aktiven Seite.  
  
```
BOOL OnSetActive();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Seite aktive erfolgreich festgelegt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Memberfunktion, um Aufgaben auszuführen, wenn eine Seite aktiviert ist. Der Außerkraftsetzung von dieser Memberfunktion rufen die Standard-Version, bevor weitere Verarbeitungsschritte ausgeführt wird.  
  
 Die Standardimplementierung gibt "true" zurück.  
  
##  <a name="onwizardback"></a>  CSnapInPropertyPageImpl::OnWizardBack  
 Diese Memberfunktion wird immer dann aufgerufen, wenn der Benutzer klickt auf die **wieder** Schaltfläche in einem Assistenten.  
  
```
BOOL OnWizardBack();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
-   0, um zur vorherigen Seite automatisch fortgefahren.  
  
-   1, um zu verhindern, dass die Seite ändern.  
  
 Geben Sie zum Springen zu einer Seite als der nächste den Bezeichner des Dialogfelds anzuzeigende zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Memberfunktion, um eine Aktion anzugeben, der Benutzer, wenn ausführen muss, die **wieder** geklickt wird.  
  
##  <a name="onwizardfinish"></a>  CSnapInPropertyPageImpl::OnWizardFinish  
 Diese Memberfunktion wird immer dann aufgerufen, wenn der Benutzer klickt auf die **Fertig stellen** Schaltfläche in einem Assistenten.  
  
```
BOOL OnWizardFinish();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn das Eigenschaftenblatt zerstört wird, wenn der Assistent abgeschlossen ist; andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Memberfunktion, um eine Aktion anzugeben, der Benutzer, wenn ausführen muss, die **Fertig stellen** geklickt wird.  
  
##  <a name="onwizardnext"></a>  CSnapInPropertyPageImpl::OnWizardNext  
 Diese Memberfunktion wird immer dann aufgerufen, wenn der Benutzer klickt auf die **Weiter** Schaltfläche in einem Assistenten.  
  
```
BOOL OnWizardNext();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
-   0, um automatisch zur nächsten Seite fortgefahren.  
  
-   1, um zu verhindern, dass die Seite ändern.  
  
 Geben Sie zum Springen zu einer Seite als der nächste den Bezeichner des Dialogfelds anzuzeigende zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Memberfunktion, um eine Aktion anzugeben, der Benutzer, wenn ausführen muss, die **Weiter** geklickt wird.  
  
##  <a name="querysiblings"></a>  CSnapInPropertyPageImpl::QuerySiblings  
 Rufen Sie diese Memberfunktion zum Weiterleiten einer Nachricht für jede Seite im Eigenschaftenblatt.  
  
```
LRESULT QuerySiblings(WPARAM wParam, LPARAM lParam);
```  
  
### <a name="parameters"></a>Parameter  
 *wParam-Parameter*  
 [in] Gibt zusätzliche Nachricht abhängige Informationen.  
  
 *lParam*  
 [in] Gibt zusätzliche Nachricht abhängige Informationen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Nachricht nicht an die nächste Eigenschaftenseite weitergeleitet werden soll; andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine Seite einen Wert ungleich NULL zurückgibt, sendet das Eigenschaftenblatt die Nachricht keine nachfolgenden Seiten.  
  
##  <a name="setmodified"></a>  CSnapInPropertyPageImpl::SetModified  
 Rufen Sie diese Memberfunktion zum Aktivieren oder Deaktivieren der **jetzt übernehmen** Schaltfläche basierend auf der gibt an, ob die Einstellungen auf der Eigenschaftenseite auf die entsprechenden externen Objekt angewendet werden soll.  
  
```
void SetModified(BOOL bChanged = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 *bChanged*  
 [in] TRUE gibt an, dass die Einstellungen für die Eigenschaftenseiten seit dem letzten geändert wurden, die sie angewendet wurden. "False", um anzugeben, dass die Einstellungen für die Eigenschaftenseiten angewendet wurden, oder ignoriert werden sollen.  
  
### <a name="remarks"></a>Hinweise  
 Das Eigenschaftenblatt verfolgt, Nachverfolgen der Seiten sind "geändert", d. h., die Eigenschaftenseiten, die für die Sie aufgerufen haben `SetModified( TRUE )`. Die **jetzt übernehmen** Schaltfläche ist immer aktiviert, wenn Sie aufrufen `SetModified( TRUE )` für eine der Seiten. Die **jetzt übernehmen** Schaltfläche wird deaktiviert, wenn Sie aufrufen `SetModified( FALSE )` für eine der Seiten, aber nur, wenn keiner der anderen Seiten "geändert" wurden ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)
