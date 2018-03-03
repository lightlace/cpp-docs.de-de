---
title: CSnapInPropertyPageImpl Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5fc1135f02c31c644d7d149900bbaa755a52c579
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="csnapinpropertypageimpl-class"></a>CSnapInPropertyPageImpl-Klasse
Diese Klasse stellt Methoden zum Implementieren einer Snap-in-Eigenschaft Page-Objekt.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
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
|[CSnapInPropertyPageImpl::CancelToClose](#canceltoclose)|Ändert den Status der **OK** und **"Abbrechen"** Schaltflächen.|  
|[CSnapInPropertyPageImpl::Create](#create)|Initialisiert eine neu erstellte `CSnapInPropertyPageImpl` Objekt.|  
|[CSnapInPropertyPageImpl::OnApply](#onapply)|Vom Framework aufgerufen, wenn der Benutzer klickt auf die **jetzt anwenden** Schaltfläche bei der Verwendung von Eigenschaftenblätter Assistenten-Typ.|  
|[CSnapInPropertyPageImpl::OnHelp](#onhelp)|Vom Framework aufgerufen, wenn der Benutzer klickt auf die **Hilfe** Schaltfläche bei der Verwendung von Eigenschaftenblätter Assistenten-Typ.|  
|[CSnapInPropertyPageImpl::OnKillActive](#onkillactive)|Vom Framework aufgerufen, wenn die aktuelle Seite nicht mehr aktiv ist.|  
|[CSnapInPropertyPageImpl::OnQueryCancel](#onquerycancel)|Vom Framework aufgerufen, wenn der Benutzer klickt auf die **"Abbrechen"** Schaltfläche und bevor der Abbruchvorgang stattgefunden hat.|  
|[CSnapInPropertyPageImpl::OnReset](#onreset)|Vom Framework aufgerufen, wenn der Benutzer klickt auf die **zurücksetzen** Schaltfläche bei der Verwendung von Eigenschaftenblätter Assistenten-Typ.|  
|[CSnapInPropertyPageImpl::OnSetActive](#onsetactive)|Vom Framework aufgerufen, wenn die aktuelle Seite aktiv ist.|  
|[CSnapInPropertyPageImpl::OnWizardBack](#onwizardback)|Vom Framework aufgerufen, wenn der Benutzer klickt auf die **wieder** Schaltfläche bei der Verwendung von Eigenschaftenblätter Assistenten-Typ.|  
|[CSnapInPropertyPageImpl::OnWizardFinish](#onwizardfinish)|Vom Framework aufgerufen, wenn der Benutzer klickt auf die **Fertig stellen** Schaltfläche bei der Verwendung von Eigenschaftenblätter Assistenten-Typ.|  
|[CSnapInPropertyPageImpl::OnWizardNext](#onwizardnext)|Vom Framework aufgerufen, wenn der Benutzer klickt auf die `Next` Schaltfläche bei der Verwendung von Eigenschaftenblätter Assistenten-Typ.|  
|[CSnapInPropertyPageImpl::QuerySiblings](#querysiblings)|Leitet die aktuelle Nachricht für alle Seiten des Eigenschaftsblatts an.|  
|[CSnapInPropertyPageImpl::SetModified](#setmodified)|Aufruf zu aktivieren oder Deaktivieren der **jetzt anwenden** Schaltfläche.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSnapInPropertyPageImpl::m_psp](#m_psp)|Die Windows **PROPSHEETPAGE** Struktur verwendet werden, indem die `CSnapInPropertyPageImpl` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 `CSnapInPropertyPageImpl`Stellt eine grundlegende Implementierung für ein Snap-in-Eigenschaft Page-Objekt. Die grundlegenden Funktionen einer Eigenschaftenseite-Snap-in werden mit mehrere Schnittstellen implementiert, und ordnen Typen.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CDialogImplBase`  
  
 `CSnapInPropertyPageImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlsnap.h  
  
##  <a name="canceltoclose"></a>CSnapInPropertyPageImpl::CancelToClose  
 Mit dieser Funktion werden, nachdem die Daten in einer Seite eines modalen Eigenschaftenblatts eine nicht behebbare Änderung vorgenommen wurde.  
  
```
void CancelToClose();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ändert sich die **OK** -Schaltfläche, um **schließen** und Deaktivieren der **"Abbrechen"** Schaltfläche. So ändern Sie Warnungen, die der Benutzer, dass eine Änderung dauerhaft und die Änderungen wird nicht abgebrochen werden kann.  
  
 Die `CancelToClose` Memberfunktion ist "nothing" in einem nicht modalen Eigenschaftenblatts, da ein nicht modalen Eigenschaftenblatts keinen hat eine **"Abbrechen"** Schaltfläche standardmäßig.  
  
##  <a name="csnapinpropertypageimpl"></a>CSnapInPropertyPageImpl::CSnapInPropertyPageImpl  
 Erstellt ein `CSnapInPropertyPageImpl`-Objekt.  
  
```
CSnapInPropertyPageImpl(LPCTSTR lpszTitle = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszTitle`  
 [in] Der Titel der Eigenschaftenseite.  
  
### <a name="remarks"></a>Hinweise  
 Um die zugrunde liegende Struktur zu initialisieren, rufen [CSnapInPropertyPageImpl::Create](#create).  
  
##  <a name="create"></a>CSnapInPropertyPageImpl::Create  
 Rufen Sie diese Funktion, um die zugrunde liegende Struktur der Eigenschaftenseite zu initialisieren.  
  
```
HPROPSHEETPAGE Create();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für ein **PROPSHEETPAGE** Struktur, die die Attribute der neu erstellte Eigenschaftenseite enthält.  
  
### <a name="remarks"></a>Hinweise  
 Sie sollten zuerst Aufrufen [CSnapInPropertyPageImpl::CSnapInPropertyPageImpl](#csnapinpropertypageimpl) vor dem Aufrufen dieser Funktion.  
  
##  <a name="m_psp"></a>CSnapInPropertyPageImpl::m_psp  
 `m_psp`ist eine Struktur, deren Mitglieder die Merkmale des speichern **PROPSHEETPAGE**.  
  
```
PROPSHEETPAGE m_psp;
```  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Struktur, um die Darstellung einer Eigenschaftenseite initialisiert werden, nachdem es erstellt wurde.  
  
 Weitere Informationen zu dieser Struktur, einschließlich einer Liste der Member, finden Sie unter [PROPSHEETPAGE](http://msdn.microsoft.com/library/aa815151) im Windows SDK.  
  
##  <a name="onapply"></a>CSnapInPropertyPageImpl::OnApply  
 Diese Memberfunktion wird aufgerufen, wenn der Benutzer klickt auf die **OK** oder **jetzt anwenden** Schaltfläche.  
  
```
BOOL OnApply();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Änderungen zulässig sind; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Vor dem `OnApply` kann aufgerufen werden, durch das Framework Sie aufgerufen hat, `SetModified` und legen Sie die Parameter auf **"true"**. Dies aktiviert die **jetzt anwenden** Schaltfläche werden, sobald der Benutzer eine Änderung auf der Eigenschaftenseite vornimmt.  
  
 Überschreiben Sie diese Memberfunktion zum angeben, welche Aktion das Programm wird, wenn der Benutzer klickt auf die **jetzt anwenden** Schaltfläche. Zum Überschreiben, sollte die Funktion zurückgeben **"true"** zum Übernehmen der Änderungen und **"false"** um zu verhindern, dass die Änderungen wirksam.  
  
 Die standardmäßige Implementierung des `OnApply` gibt **"true"**.  
  
##  <a name="onhelp"></a>CSnapInPropertyPageImpl::OnHelp  
 Diese Memberfunktion wird aufgerufen, wenn der Benutzer klickt auf die **Hilfe** Schaltfläche für die Eigenschaftsseite ".  
  
```
void OnHelp();
```  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Memberfunktion zum Anzeigen der Hilfe für die Eigenschaftsseite ".  
  
##  <a name="onkillactive"></a>CSnapInPropertyPageImpl::OnKillActive  
 Diese Memberfunktion wird aufgerufen, wenn die Seite nicht mehr die aktive Seite ist.  
  
```
BOOL OnKillActive();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Daten erfolgreich aktualisiert wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Memberfunktion, um spezielle Data Validation Aufgaben auszuführen.  
  
##  <a name="onquerycancel"></a>CSnapInPropertyPageImpl::OnQueryCancel  
 Diese Memberfunktion wird aufgerufen, wenn der Benutzer klickt auf die **"Abbrechen"** Schaltfläche und bevor der Abbruchvorgang Aktion stattgefunden hat.  
  
```
BOOL OnQueryCancel();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich, wenn der Vorgang "Abbrechen" zugelassen; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Memberfunktion, um eine Aktion anzugeben, das Programm akzeptiert, wenn der Benutzer klickt auf, die **"Abbrechen"** Schaltfläche.  
  
 Die standardmäßige Implementierung des `OnQueryCancel` gibt **"true"**.  
  
##  <a name="onreset"></a>CSnapInPropertyPageImpl::OnReset  
 Diese Memberfunktion wird aufgerufen, wenn der Benutzer klickt auf die **"Abbrechen"** Schaltfläche.  
  
```
void OnReset();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn diese Funktion aufgerufen wird, ändert sich in allen Eigenschaftenseiten, die durch den Benutzer, die Sie zuvor auf vorgenommen wurden die **jetzt anwenden** Schaltfläche werden verworfen, und das Eigenschaftenblatt behält den Fokus.  
  
 Überschreiben Sie diese Memberfunktion zum angeben, welche Aktion das Programm akzeptiert, wenn der Benutzer klickt auf die **"Abbrechen"** Schaltfläche.  
  
##  <a name="onsetactive"></a>CSnapInPropertyPageImpl::OnSetActive  
 Diese Memberfunktion wird aufgerufen, wenn die Seite vom Benutzer ausgewählt wird und als aktive Seite.  
  
```
BOOL OnSetActive();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn die Seite active festgelegt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Memberfunktion, um Aufgaben auszuführen, wenn eine Seite aktiviert wird. Die Außerkraftsetzung von dieser Memberfunktion sollten die Standardversion aufrufen, bevor weitere Verarbeitungsschritte ausgeführt wird.  
  
 Gibt die standardmäßige Implementierung **"true"**.  
  
##  <a name="onwizardback"></a>CSnapInPropertyPageImpl::OnWizardBack  
 Diese Memberfunktion wird aufgerufen, wenn der Benutzer klickt auf die **wieder** Schaltfläche in einem Assistenten.  
  
```
BOOL OnWizardBack();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
-   0 bis automatisch zur vorherigen Seite zu gelangen.  
  
-   1, um zu verhindern, dass die Seite ändern.  
  
 Geben Sie zum Springen zu einer Seite als der nächste zurück den Bezeichner des Dialogfelds angezeigt werden.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Memberfunktion, um eine Aktion anzugeben, der Benutzer muss beim Ausführen, der **wieder** geklickt wird.  
  
##  <a name="onwizardfinish"></a>CSnapInPropertyPageImpl::OnWizardFinish  
 Diese Memberfunktion wird aufgerufen, wenn der Benutzer klickt auf die **Fertig stellen** Schaltfläche in einem Assistenten.  
  
```
BOOL OnWizardFinish();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Eigenschaftenfenster zerstört wird, nach Abschluss des Assistenten; andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Memberfunktion, um eine Aktion anzugeben, der Benutzer muss beim Ausführen, der **Fertig stellen** geklickt wird.  
  
##  <a name="onwizardnext"></a>CSnapInPropertyPageImpl::OnWizardNext  
 Diese Memberfunktion wird aufgerufen, wenn der Benutzer klickt auf die `Next` Schaltfläche in einem Assistenten.  
  
```
BOOL OnWizardNext();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
-   0 bis automatisch zur nächsten Seite zu gelangen.  
  
-   1, um zu verhindern, dass die Seite ändern.  
  
 Geben Sie zum Springen zu einer Seite als der nächste zurück den Bezeichner des Dialogfelds angezeigt werden.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Memberfunktion, um eine Aktion anzugeben, der Benutzer muss beim Ausführen, der `Next` Schaltfläche geklickt wird.  
  
##  <a name="querysiblings"></a>CSnapInPropertyPageImpl::QuerySiblings  
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
 Wert ungleich NULL, wenn die Nachricht an die nächste Eigenschaftenseite nicht weitergeleitet werden soll; andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine Seite einen Wert ungleich NULL zurückgibt, sendet Eigenschaftenblatt die Nachricht keine nachfolgenden Seiten.  
  
##  <a name="setmodified"></a>CSnapInPropertyPageImpl::SetModified  
 Rufen Sie diese Memberfunktion zum Aktivieren oder Deaktivieren der **jetzt anwenden** Schaltfläche basierend auf, ob die Einstellungen auf der Eigenschaftenseite auf die entsprechenden externen Objekt angewendet werden soll.  
  
```
void SetModified(BOOL bChanged = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bChanged`  
 [in] **"True"** , um anzugeben, dass die eigenschafteneinstellungen für die Seite sie angewendet wurden, seit der letzten Ausführung geändert wurde **"False"** angeben, dass die eigenschafteneinstellungen angewendet wurden, oder ignoriert werden sollen.  
  
### <a name="remarks"></a>Hinweise  
 Eigenschaftenblatt beibehält, Nachverfolgen der Seiten werden "unsaubere", d. h., die Eigenschaftenseiten für das Sie aufgerufen haben **SetModified (TRUE)**. Die **jetzt anwenden** Schaltfläche wird immer aktiviert, wenn Sie rufen **SetModified (TRUE)** für eine der Seiten. Die **jetzt anwenden** Schaltfläche wird deaktiviert, wenn Sie aufrufen **SetModified (FALSE)** für eine der Seiten, aber nur wenn Sie keines der anderen Seiten "unsaubere".  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../../atl/atl-class-overview.md)
