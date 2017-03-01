---
title: Klasse CSnapInPropertyPageImpl | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSnapInPropertyPageImpl
dev_langs:
- C++
helpviewer_keywords:
- snap-ins, property pages
- snap-ins
- property pages, ATL
- CSnapInPropertyPageImpl class
ms.assetid: 75bdce5a-985e-4166-bd44-493132e023c4
caps.latest.revision: 20
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
translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: f5db4d0742a423e9574db2a4268a9376491b2ed2
ms.lasthandoff: 02/24/2017

---
# <a name="csnapinpropertypageimpl-class"></a>CSnapInPropertyPageImpl-Klasse
Diese Klasse stellt Methoden zum Implementieren einer Snap-in-Eigenschaft Page-Objekt.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
CSnapInPropertyPageImpl : public CDialogImplBase
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSnapInPropertyPageImpl::CSnapInPropertyPageImpl](#csnapinpropertypageimpl)|Konstruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSnapInPropertyPageImpl::CancelToClose](#canceltoclose)|Ändert den Status der **OK** und **Abbrechen** Schaltflächen.|  
|[CSnapInPropertyPageImpl::Create](#create)|Initialisiert eine neu erstellte `CSnapInPropertyPageImpl` Objekt.|  
|[CSnapInPropertyPageImpl::OnApply](#onapply)|Vom Framework aufgerufen, wenn der Benutzer klickt auf die **jetzt** Schaltfläche beim Verwenden des Eigenschaftenfensters Assistent-Typ.|  
|[CSnapInPropertyPageImpl::OnHelp](#onhelp)|Vom Framework aufgerufen, wenn der Benutzer klickt auf die **Hilfe** Schaltfläche beim Verwenden des Eigenschaftenfensters Assistent-Typ.|  
|[CSnapInPropertyPageImpl::OnKillActive](#onkillactive)|Wird vom Framework aufgerufen, wenn die aktuelle Seite nicht mehr aktiv ist.|  
|[CSnapInPropertyPageImpl::OnQueryCancel](#onquerycancel)|Vom Framework aufgerufen, wenn der Benutzer klickt auf die **Abbrechen** Schaltfläche und bevor der Abbruchvorgang stattgefunden hat.|  
|[CSnapInPropertyPageImpl::OnReset](#onreset)|Vom Framework aufgerufen, wenn der Benutzer klickt auf die **zurücksetzen** Schaltfläche beim Verwenden des Eigenschaftenfensters Assistent-Typ.|  
|[CSnapInPropertyPageImpl::OnSetActive](#onsetactive)|Vom Framework aufgerufen, wenn die aktuelle Seite aktiv ist.|  
|[CSnapInPropertyPageImpl::OnWizardBack](#onwizardback)|Vom Framework aufgerufen, wenn der Benutzer klickt auf die **wieder** beim Verwenden des Eigenschaftenfensters Assistententyp Schaltfläche.|  
|[CSnapInPropertyPageImpl::OnWizardFinish](#onwizardfinish)|Vom Framework aufgerufen, wenn der Benutzer klickt auf die **Fertig stellen** Schaltfläche beim Verwenden des Eigenschaftenfensters Assistent-Typ.|  
|[CSnapInPropertyPageImpl::OnWizardNext](#onwizardnext)|Vom Framework aufgerufen, wenn der Benutzer klickt auf die `Next` Schaltfläche beim Verwenden des Eigenschaftenfensters Assistent-Typ.|  
|[CSnapInPropertyPageImpl::QuerySiblings](#querysiblings)|Leitet die aktuelle Nachricht für alle Seiten im Eigenschaftenblatt.|  
|[CSnapInPropertyPageImpl::SetModified](#setmodified)|Aufruf von aktivieren oder Deaktivieren der **jetzt** Schaltfläche.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSnapInPropertyPageImpl::m_psp](#m_psp)|Windows **PROPSHEETPAGE** Struktur anhand der `CSnapInPropertyPageImpl` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 `CSnapInPropertyPageImpl`Stellt eine grundlegende Implementierung für ein Snap-in-Eigenschaft Page-Objekt. Die grundlegenden Funktionen einer Eigenschaftenseite-Snap-in werden mithilfe von mehrere Schnittstellen implementiert und Zuordnen von Typen.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CDialogImplBase`  
  
 `CSnapInPropertyPageImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlsnap.h  
  
##  <a name="a-namecanceltoclosea--csnapinpropertypageimplcanceltoclose"></a><a name="canceltoclose"></a>CSnapInPropertyPageImpl::CancelToClose  
 Rufen Sie diese Funktion aus, nachdem die Daten in eine Seite mit einem modalen Eigenschaftenblatt eine nicht behebbare Änderung vorgenommen wurde.  
  
```
void CancelToClose();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ändert die **OK** -Schaltfläche, um **schließen** und Deaktivieren der **Abbrechen** Schaltfläche. So ändern Sie Warnungen, die der Benutzer, dass eine Änderung dauerhaft und die Änderungen rückgängig gemacht werden kann.  
  
 Die `CancelToClose` Memberfunktion "nothing" in einem nicht modalen Eigenschaftenblatts, da kein nicht modalen Eigenschaftenblatts kein **Abbrechen** Schaltfläche standardmäßig.  
  
##  <a name="a-namecsnapinpropertypageimpla--csnapinpropertypageimplcsnapinpropertypageimpl"></a><a name="csnapinpropertypageimpl"></a>CSnapInPropertyPageImpl::CSnapInPropertyPageImpl  
 Erstellt ein `CSnapInPropertyPageImpl`-Objekt.  
  
```
CSnapInPropertyPageImpl(LPCTSTR lpszTitle = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszTitle`  
 [in] Der Titel der Eigenschaftenseite.  
  
### <a name="remarks"></a>Hinweise  
 Aufrufen, um die zugrunde liegende Struktur zu initialisieren, [CSnapInPropertyPageImpl::Create](#create).  
  
##  <a name="a-namecreatea--csnapinpropertypageimplcreate"></a><a name="create"></a>CSnapInPropertyPageImpl::Create  
 Rufen Sie diese Funktion, um die zugrunde liegende Struktur der Seite zu initialisieren.  
  
```
HPROPSHEETPAGE Create();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für ein **PROPSHEETPAGE** -Struktur, die die Attribute der neu erstellte Eigenschaftenseite enthält.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie zuerst [CSnapInPropertyPageImpl::CSnapInPropertyPageImpl](#csnapinpropertypageimpl) vor dem Aufruf dieser Funktion.  
  
##  <a name="a-namempspa--csnapinpropertypageimplmpsp"></a><a name="m_psp"></a>CSnapInPropertyPageImpl::m_psp  
 `m_psp`ist eine Struktur, deren Mitglieder die Merkmale des speichern **PROPSHEETPAGE**.  
  
```
PROPSHEETPAGE m_psp;
```  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Struktur, um die Darstellung einer Eigenschaftenseite zu initialisieren, sobald es erstellt wurde.  
  
 Weitere Informationen zu dieser Struktur, die eine Auflistung von Membern, einschließlich finden Sie unter [PROPSHEETPAGE](http://msdn.microsoft.com/library/aa815151) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameonapplya--csnapinpropertypageimplonapply"></a><a name="onapply"></a>CSnapInPropertyPageImpl::OnApply  
 Diese Member-Funktion wird aufgerufen, wenn der Benutzer klickt auf die **OK** oder **jetzt** Schaltfläche.  
  
```
BOOL OnApply();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Änderungen akzeptiert werden; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Vor dem `OnApply` kann aufgerufen werden, durch das Framework Sie aufgerufen hat, `SetModified` und legen Sie den Parameter auf **TRUE**. Dies aktiviert die **jetzt** Schaltfläche, sobald der Benutzer eine Änderung auf der Eigenschaftenseite vornimmt.  
  
 Überschreiben Sie diese Memberfunktion, um das Programm gibt, klickt der Benutzer angeben, welche Aktion der **jetzt** Schaltfläche. Beim Überschreiben von die Funktion zurückgeben sollte **TRUE** um Änderungen zu übernehmen und **FALSE** verhindern, dass die Änderungen wirksam.  
  
 Die standardmäßige Implementierung des `OnApply` gibt **TRUE**.  
  
##  <a name="a-nameonhelpa--csnapinpropertypageimplonhelp"></a><a name="onhelp"></a>CSnapInPropertyPageImpl::OnHelp  
 Diese Member-Funktion wird aufgerufen, wenn der Benutzer klickt auf die **Hilfe** Schaltfläche für die Eigenschaftenseite.  
  
```
void OnHelp();
```  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Memberfunktion zum Anzeigen der Hilfe für die Eigenschaftenseite.  
  
##  <a name="a-nameonkillactivea--csnapinpropertypageimplonkillactive"></a><a name="onkillactive"></a>CSnapInPropertyPageImpl::OnKillActive  
 Diese Member-Funktion wird aufgerufen, wenn die Seite nicht mehr die aktive Seite ist.  
  
```
BOOL OnKillActive();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Daten erfolgreich aktualisiert wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Memberfunktion Objektdaten Validierung Aufgaben.  
  
##  <a name="a-nameonquerycancela--csnapinpropertypageimplonquerycancel"></a><a name="onquerycancel"></a>CSnapInPropertyPageImpl::OnQueryCancel  
 Diese Member-Funktion wird aufgerufen, wenn der Benutzer klickt auf die **Abbrechen** Schaltfläche und vor dem Abbrechen Aktion stattgefunden hat.  
  
```
BOOL OnQueryCancel();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL an den Vorgang abbrechen können; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Member-Funktion, um eine Aktion anzugeben, das Programm akzeptiert, klickt der Benutzer, die **Abbrechen** Schaltfläche.  
  
 Die standardmäßige Implementierung des `OnQueryCancel` gibt **TRUE**.  
  
##  <a name="a-nameonreseta--csnapinpropertypageimplonreset"></a><a name="onreset"></a>CSnapInPropertyPageImpl::OnReset  
 Diese Member-Funktion wird aufgerufen, wenn der Benutzer klickt auf die **Abbrechen** Schaltfläche.  
  
```
void OnReset();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn diese Funktion aufgerufen wird, ändert sich in alle Eigenschaftenseiten, die vorgenommen wurden, durch den Benutzer, die Sie zuvor auf die **jetzt** Schaltfläche werden verworfen, und das Eigenschaftenfenster behält den Fokus.  
  
 Überschreiben Sie diese Memberfunktion zum angeben, welche Aktion das Programm akzeptiert, klickt der Benutzer die **Abbrechen** Schaltfläche.  
  
##  <a name="a-nameonsetactivea--csnapinpropertypageimplonsetactive"></a><a name="onsetactive"></a>CSnapInPropertyPageImpl::OnSetActive  
 Diese Member-Funktion wird aufgerufen, wenn die Seite vom Benutzer ausgewählt und wird die aktive Seite.  
  
```
BOOL OnSetActive();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Seite erfolgreich aktiviert wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Memberfunktion, um Aufgaben auszuführen, wenn eine Seite aktiviert wird. Die Überschreibung von dieser Memberfunktion sollten die Standardversion aufrufen, bevor eine andere Verarbeitung erfolgt.  
  
 Die standardmäßige Implementierung gibt **TRUE**.  
  
##  <a name="a-nameonwizardbacka--csnapinpropertypageimplonwizardback"></a><a name="onwizardback"></a>CSnapInPropertyPageImpl::OnWizardBack  
 Diese Member-Funktion wird aufgerufen, wenn der Benutzer klickt auf die **wieder** Schaltfläche in einem Assistenten.  
  
```
BOOL OnWizardBack();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
-   0 bis automatisch zur vorherigen Seite zu gelangen.  
  
-   1, um zu verhindern, dass die Seite ändern.  
  
 Geben Sie zum Anzeigen einer Seite als nächste zurück des Bezeichners des Dialogfelds angezeigt werden.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Member-Funktion, um eine Aktion anzugeben, der Benutzer muss beim Ausführen, der **wieder** geklickt wird.  
  
##  <a name="a-nameonwizardfinisha--csnapinpropertypageimplonwizardfinish"></a><a name="onwizardfinish"></a>CSnapInPropertyPageImpl::OnWizardFinish  
 Diese Member-Funktion wird aufgerufen, wenn der Benutzer klickt auf die **Fertig stellen** Schaltfläche in einem Assistenten.  
  
```
BOOL OnWizardFinish();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Eigenschaftenfenster zerstört wird, wenn der Assistent abgeschlossen ist; andernfalls&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Member-Funktion, um eine Aktion anzugeben, der Benutzer muss beim Ausführen, der **Fertig stellen** geklickt wird.  
  
##  <a name="a-nameonwizardnexta--csnapinpropertypageimplonwizardnext"></a><a name="onwizardnext"></a>CSnapInPropertyPageImpl::OnWizardNext  
 Diese Member-Funktion wird aufgerufen, wenn der Benutzer klickt auf die `Next` Schaltfläche in einem Assistenten.  
  
```
BOOL OnWizardNext();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
-   0 bis automatisch zur nächsten Seite zu gelangen.  
  
-   1, um zu verhindern, dass die Seite ändern.  
  
 Geben Sie zum Anzeigen einer Seite als nächste zurück des Bezeichners des Dialogfelds angezeigt werden.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Member-Funktion, um eine Aktion anzugeben, der Benutzer muss beim Ausführen, der `Next` geklickt wird.  
  
##  <a name="a-namequerysiblingsa--csnapinpropertypageimplquerysiblings"></a><a name="querysiblings"></a>CSnapInPropertyPageImpl::QuerySiblings  
 Rufen Sie diese Memberfunktion zum Weiterleiten einer Nachricht auf jeder Seite im Eigenschaftenblatt.  
  
```
LRESULT QuerySiblings(WPARAM wParam, LPARAM lParam);
```  
  
### <a name="parameters"></a>Parameter  
 `wParam`  
 [in] Gibt zusätzliche Nachricht abhängige Informationen.  
  
 `lParam`  
 [in] Gibt zusätzliche Nachricht abhängige Informationen.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Nachricht nicht soll, können Sie die nächste Seite der Eigenschaft weitergeleitet werden; andernfalls&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine Seite einen Wert ungleich NULL zurückgibt, sendet das Eigenschaftenblatt die Nachricht keine nachfolgenden Seiten.  
  
##  <a name="a-namesetmodifieda--csnapinpropertypageimplsetmodified"></a><a name="setmodified"></a>CSnapInPropertyPageImpl::SetModified  
 Rufen Sie diese Memberfunktion zum Aktivieren oder Deaktivieren der **jetzt** Schaltfläche, ob die Einstellungen auf der Eigenschaftenseite auf die entsprechenden externen Objekt angewendet werden soll.  
  
```
void SetModified(BOOL bChanged = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bChanged`  
 [in] **TRUE** an, dass die Einstellungen für die Eigenschaft sie angewendet wurden, seit der letzten geändert wurden **FALSE** angeben, dass die Einstellungen für die Eigenschaft angewendet wurden oder ignoriert werden sollen.  
  
### <a name="remarks"></a>Hinweise  
 Das Eigenschaftenblatt verfolgt, Nachverfolgen der Seiten sind "fehlerhaft" anzeigt, d. h., die Eigenschaftenseiten für die Sie aufgerufen haben **SetModified (TRUE)**. Die **jetzt** Schaltfläche ist immer aktiviert, wenn Sie aufrufen **SetModified (TRUE)** für eine der Seiten. Die **jetzt** Schaltfläche wird deaktiviert, wenn Sie aufrufen **SetModified (FALSE)** für eine der Seiten, aber nur, wenn ist keine der anderen Seiten "unsaubere".  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

