---
title: Anwendungssteuerelement | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- application control
ms.assetid: c1f69f15-e0fe-4515-9f36-d63d31869deb
caps.latest.revision: 12
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
ms.sourcegitcommit: b943ef8dd652df061965fe81ecc9c08115636141
ms.openlocfilehash: 5e48437920f56cdfd119c1d703db585616881833
ms.contentlocale: de-de
ms.lasthandoff: 04/04/2017

---
# <a name="application-control"></a>Anwendungssteuerelement
OLE erfordert erhebliche Kontrolle über die Anwendungen und ihre Objekte. Die OLE-System-DLLs muss vorliegen zum Starten und Anwendungen automatisch freigeben, koordinieren ihre Produktions- und Änderung von Objekten und so weiter. Die Funktionen in diesem Thema werden diese Anforderungen erfüllen. Zusätzlich zu den von der OLE-System-DLLs aufgerufen werden, müssen diese Funktionen in einigen Fällen von Anwendungen sowie aufgerufen werden. 
  
### <a name="application-control"></a>Anwendungssteuerelement  
  
|||  
|-|-|  
|[AfxOleCanExitApp](#afxolecanexitapp)|Gibt an, ob die Anwendung beenden kann.|  
|[AfxOleGetMessageFilter](#afxolegetmessagefilter)|Ruft die Anwendung aktuelle Meldungsfilter ab.|  
|[AfxOleGetUserCtrl](#afxolegetuserctrl)|Ruft das aktuelle Benutzersteuerelement Flag ab.|  
|[AfxOleSetUserCtrl](#afxolesetuserctrl)|Löscht das Benutzersteuerelement Flag ab oder legt ihn fest.|  
|[AfxOleLockApp](#afxolelockapp)|Erhöht das Framework globale Anzahl von aktiven Objekten in einer Anwendung.|  
|[AfxOleLockControl](#afxolelockcontrol)| Sperrt die Klassenfactory des angegebenen Steuerelements. |
|[AfxOleUnlockApp](#afxoleunlockapp)|Verringert das Framework die Anzahl von aktiven Objekten in einer Anwendung.| 
|[AfxOleUnlockControl](#afxoleunlockcontrol)| Entsperrt die Klassenfactory des angegebenen Steuerelements. |
|[AfxOleRegisterServerClass](#afxoleregisterserverclass)|Registriert einen Server in der OLE-systemregistrierung.|  
|[AfxOleSetEditMenu](#afxoleseteditmenu)|Implementiert die Benutzeroberfläche für die *Typename* Objekt-Befehl.|  

  
##  <a name="afxolecanexitapp"></a>AfxOleCanExitApp  
 Gibt an, ob die Anwendung beenden kann.  
  
```   
BOOL AFXAPI AfxOleCanExitApp(); 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Anwendung beendet werden kann; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Eine Anwendung sollen nicht beendet werden, wenn ausstehende Verweise auf seine Objekte vorhanden sind. Die globalen Funktionen `AfxOleLockApp` und `AfxOleUnlockApp` Inkrementieren und Dekrementieren bzw. einen Zähler der Verweise auf Objekte von der Anwendung. Die Anwendung sollen nicht beendet werden, wenn dieser Leistungsindikator ungleich NULL ist. Wenn der Leistungsindikator ungleich NULL ist, wird im Hauptfenster der Anwendung (nicht-getrennt) ausgeblendet, wenn der Benutzer aus dem Systemmenü oder über das Menü Datei beenden schließen auswählt. Das Framework ruft diese Funktion **CFrameWnd::OnClose**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCAutomation #2](../../mfc/codesnippet/cpp/application-control_1.cpp)]  

## <a name="requirements"></a>Anforderungen  
 **Header**: afxdisp.h 

##  <a name="afxolegetmessagefilter"></a>AfxOleGetMessageFilter  
 Ruft die Anwendung aktuelle Meldungsfilter ab.  
  
```   
COleMessageFilter* AFXAPI AfxOleGetMessageFilter(); 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den aktuellen Nachrichtenfilter.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird für den Zugriff auf die aktuelle `COleMessageFilter`-Objekt, abgeleitet, wie Sie aufrufen `AfxGetApp` auf das aktuelle Anwendungsobjekt zugreifen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCAutomation Nr. 3](../../mfc/codesnippet/cpp/application-control_2.cpp)]  
  
 [!code-cpp[NVC_MFCAutomation #4](../../mfc/codesnippet/cpp/application-control_3.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header**: afxwin.h 

##  <a name="afxolegetuserctrl"></a>AfxOleGetUserCtrl  
 Ruft das aktuelle Benutzersteuerelement Flag ab.  
  
```   
BOOL AFXAPI AfxOleGetUserCtrl(); 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Benutzer im Steuerelement der Anwendung ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Der Benutzer ist im Steuerelement der Anwendung, wenn der Benutzer explizit geöffnet oder erstellt ein neues Dokument. Der Benutzer ist auch im Steuerelement, wenn die Anwendung durch die OLE-System-DLLs nicht gestartet wurde – das heißt, wenn der Benutzer die Anwendung mit der Shell System gestartet.  

### <a name="requirements"></a>Anforderungen  
 **Header**: afxdisp.h

##  <a name="afxolesetuserctrl"></a>AfxOleSetUserCtrl  
 Legt fest oder löscht das Benutzersteuerelement Flag auf, der in der Referenz für beschrieben wird `AfxOleGetUserCtrl`.  
  
```  
void AFXAPI AfxOleSetUserCtrl(BOOL bUserCtrl); 
```  
  
### <a name="parameters"></a>Parameter  
 *bUserCtrl*  
 Gibt an, ob das Benutzersteuerelement Flag festgelegt oder gelöscht werden.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Funktion, wenn der Benutzer erstellt oder ein Dokument lädt, jedoch nicht, wenn ein Dokument geladen oder durch einen indirekten Maßnahmen erstellt wie das Laden von einem eingebetteten Objekt in eine Steuerelementcontainer-Anwendung.  
  
 Rufen Sie diese Funktion, wenn andere Aktionen in der Anwendung den Benutzer Kontrolle über die Anwendung eingefügt werden soll.  

### <a name="requirements"></a>Anforderungen  
 **Header**: afxdisp.h

##  <a name="afxolelockapp"></a>AfxOleLockApp  
 Erhöht das Framework globale Anzahl von aktiven Objekten in der Anwendung an.  
  
```   
void AFXAPI AfxOleLockApp(); 
```  
  
### <a name="remarks"></a>Hinweise  
 Das Framework wird die Anzahl von Objekten in einer Anwendung aktiv gehalten. Die `AfxOleLockApp` und `AfxOleUnlockApp` Funktionen, bzw. Inkrementieren und Dekrementieren diese Zahl.  
  
 Wenn der Benutzer versucht, eine Anwendung zu schließen, die aktive Objekte verfügt – eine Anwendung, für die die Anzahl von aktiven Objekten ungleich NULL ist: das Framework Blendet Sie aus der Anwendung aus Sicht des Benutzers, vollständig heruntergefahren. Die `AfxOleCanExitApp` -Funktion zeigt an, ob die Anwendung beenden kann.  
  
 Rufen Sie `AfxOleLockApp` aller Objekte, die OLE-Schnittstellen verfügbar macht, wenn es nicht wünschenswert, dass das Objekt zerstört werden, während noch von einer Clientanwendung verwendet werden könnten. Rufen Sie auch `AfxOleUnlockApp` im Destruktor der jedes Objekt, das Aufrufe `AfxOleLockApp` im Konstruktor. Standardmäßig `COleDocument` (und abgeleitete Klassen) automatisch sperren und Entsperren von der Anwendung.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCAutomation Nr. 5](../../mfc/codesnippet/cpp/application-control_4.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header**: afxdisp.h

##  <a name="afxoleunlockapp"></a>AfxOleUnlockApp  
 Dekrementiert den Wert der Framework-Anzahl von aktiven Objekten in der Anwendung.  
  
```   
void AFXAPI AfxOleUnlockApp(); 
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter `AfxOleLockApp` für Weitere Informationen zu erhalten.  
  
 Wenn die Anzahl von aktiven Objekten NULL ist, erreicht **AfxOleOnReleaseAllObjects** aufgerufen wird.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [AfxOleLockApp](#afxolelockapp).  

### <a name="requirements"></a>Anforderungen  
 **Header**: afxdisp.h  

 ## <a name="afxolelockcontrol"></a>AfxOleLockControl
Sperrt die Klassenfactory des angegebenen Steuerelements an, sodass dynamisch erstellte mit dem Steuerelement verknüpfte Daten im Arbeitsspeicher bleibt.  
   
### <a name="syntax"></a>Syntax    
```
BOOL AFXAPI AfxOleLockControl(  REFCLSID clsid  );  
BOOL AFXAPI AfxOleLockControl( LPCTSTR lpszProgID );  
```
### <a name="parameters"></a>Parameter  
 `clsid`  
 Die eindeutige Klassen-ID des Steuerelements.  
  
 `lpszProgID`  
 Die eindeutige Programm-ID des Steuerelements.  
   
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Klassenfactory des Steuerelements erfolgreich gesperrt wurde; andernfalls 0.  
   
### <a name="remarks"></a>Hinweise  
 Dadurch können Sie die Anzeige der Steuerelemente deutlich beschleunigen. Beispielsweise einmal Sie ein Steuerelement in einem Dialogfeld erstellen und Sperren Sie das Steuerelement mit `AfxOleLockControl`, Sie müssen nicht zum Erstellen und es dann erneut kill, jedes Mal, wenn das Dialogfeld angezeigt oder zerstört wird. Wenn der Benutzer öffnet und ein Dialogfeld, wiederholt schließt, kann die Steuerelemente sperren erheblich verbessern. Wenn Sie das Steuerelement löschen möchten, rufen Sie `AfxOleUnlockControl`.  
   
### <a name="example"></a>Beispiel  
```cpp
// Starts and locks control's (Microsoft Calendar) class factory. 
// Control will remain in memory for lifetime of
// application or until AfxOleUnlockControl() is called.

AfxOleLockControl(_T("MSCAL.Calendar"));
```
   
### <a name="requirements"></a>Anforderungen  
 **Header:**<afxwin.h></afxwin.h>  
   
### <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](mfc-macros-and-globals.md)   
 [AfxOleUnlockControl](#afxoleunlockcontrol)
 
##  <a name="afxoleregisterserverclass"></a>AfxOleRegisterServerClass  
 Mit dieser Funktion können Sie zum Registrieren Ihres Servers in der OLE-systemregistrierung.  
  
```   
BOOL AFXAPI AfxOleRegisterServerClass(
    REFCLSID clsid,  
    LPCTSTR lpszClassName,  
    LPCTSTR lpszShortTypeName,  
    LPCTSTR lpszLongTypeName,  
    OLE_APPTYPE nAppType = OAT_SERVER,  
    LPCTSTR* rglpszRegister = NULL,  
    LPCTSTR* rglpszOverwrite = NULL); 
```  
  
### <a name="parameters"></a>Parameter  
 `clsid`  
 Verweis auf den Server OLE-Klassen-ID.  
  
 `lpszClassName`  
 Ein Zeiger auf eine Zeichenfolge, die den Klassennamen von Objekten des Servers enthält.  
  
 *lpszShortTypeName*  
 Zeiger auf eine Zeichenfolge mit den kurzen Namen des Objekttyps des Servers, z. B. "Diagramm".  
  
 *lpszLongTypeName*  
 Zeiger auf eine Zeichenfolge, enthält den langen Namen des Objekttyps des Servers, z. B. "Microsoft Excel 5.0 Chart".  
  
 `nAppType`  
 Ein Wert aus der **OLE_APPTYPE** Enumeration, die Angabe des Typs der OLE-Anwendung. Mögliche Werte sind die folgenden:  
  
- `OAT_INPLACE_SERVER`Server hat vollständige Server-Benutzeroberfläche.  
  
- `OAT_SERVER`Server unterstützt nur einbetten.  
  
- `OAT_CONTAINER`Container unterstützt Links zu einbettungen.  
  
- `OAT_DISPATCH_OBJECT``IDispatch`-fähigen Objekt.  
  
 `rglpszRegister`  
 Array von Zeigern auf Zeichenfolgen, die die Schlüssel und Werte der OLE-System-Registrierung hinzugefügt werden, wenn keine vorhandenen Werte für die Schlüssel nicht gefunden werden.  
  
 `rglpszOverwrite`  
 Array von Zeigern auf Zeichenfolgen, die die Schlüssel und Werte der OLE-System-Registrierung hinzugefügt werden, wenn es sich bei die Registrierung vorhandene Werte für den angegebenen Schlüssel enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Klasse des Servers erfolgreich registriert ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die meisten Anwendungen verwenden können **COleTemplateServer::Register** Dokumenttypen für die Anwendung zu registrieren. Wenn Ihre Anwendung systemregistrierung Format nicht das normale Muster passt, können Sie `AfxOleRegisterServerClass` mehr Kontrolle.  
  
 Die Registrierung besteht aus einem Satz von Schlüsseln und Werten. Die `rglpszRegister` und `rglpszOverwrite` Argumente sind Arrays von Zeigern auf Zeichenfolgen, bestehend aus einem Schlüssel und einem Wert durch voneinander getrennte eine **NULL** Zeichen ( `'\0'`). Die einzelnen Zeichenfolgen können ersetzbare Parameter, deren Stellen durch die Zeichensequenzen gekennzeichnet sind `%1` über `%5`.  
  
 Die Symbole sind wie folgt ausgefüllt:  
  
|Symbol|Wert|  
|------------|-----------|  
|%1|Klassen-ID als Zeichenfolge formatiert|  
|%2|Klassenname|  
|%3|Pfad zur ausführbaren Datei|  
|%4|Kurze Typname|  
|%5|Vom Typ Long name|  

### <a name="requirements"></a>Anforderungen  
 **Header**: afxdisp.h

##  <a name="afxoleseteditmenu"></a>AfxOleSetEditMenu  
 Implementiert die Benutzeroberfläche für die *Typename* Objekt-Befehl.  
  
```   
void AFXAPI AfxOleSetEditMenu(
    COleClientItem* pClient,  
    CMenu* pMenu,  
    UINT iMenuItem,  
    UINT nIDVerbMin,  
    UINT nIDVerbMax = 0,  
    UINT nIDConvert = 0); 
```  
  
### <a name="parameters"></a>Parameter  
 `pClient`  
 Ein Zeiger auf das Client-OLE-Element.  
  
 `pMenu`  
 Ein Zeiger auf das Menu-Objekt aktualisiert werden.  
  
 *iMenuItem*  
 Der Index des Menüelements aktualisiert werden.  
  
 `nIDVerbMin`  
 Die Befehls-ID, die das primäre Verb entspricht.  
  
 *nIDVerbMax*  
 Die Befehls-ID, die bis zum letzten Verb entspricht.  
  
 *nIDConvert*  
 Die ID für das Menüelement konvertieren.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Server nur ein primäres Verb erkennt, wird das Menüelement "Verb *Typename* Objekt" und der `nIDVerbMin` -Befehl gesendet wird, wenn der Benutzer den Befehl auswählt. Wenn der Server erkennt mehrere Verben, wird das Menüelement " *Typename* Objekt" und ein Untermenü mit alle Verben wird angezeigt, wenn der Benutzer den Befehl auswählt. Wenn der Benutzer im Untermenü ein Verb auswählt `nIDVerbMin` wird gesendet, wenn das erste Verb ausgewählt wird, `nIDVerbMin` + 1 wird gesendet, wenn das zweite Verb ausgewählte usw. ist. Die Standardeinstellung `COleDocument` Implementierung behandelt automatisch diese Funktion.  
  
 Sie benötigen die folgende Anweisung im Ressourcenskript für Ihre Client-Anwendung (. RC)-Datei:  
  
 **#include \<afxolecl.rc >**  

### <a name="requirements"></a>Anforderungen  
 **Header**: afxole.h 

## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)

## <a name="afxoleunlockcontrol"></a>AfxOleUnlockControl
Entsperrt die Klassenfactory des angegebenen Steuerelements.  
   
### <a name="syntax"></a>Syntax  
  ```
BOOL AFXAPI AfxOleUnlockControl( REFCLSID clsid );  
BOOL AFXAPI AfxOleUnlockControl( LPCTSTR lpszProgID );  
```
### <a name="parameters"></a>Parameter  
 `clsid`  
 Die eindeutige Klassen-ID des Steuerelements.  
  
 `lpszProgID`  
 Die eindeutige Programm-ID des Steuerelements.  
   
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Klassenfactory des Steuerelements erfolgreich entsperrt wurde; andernfalls 0.  
   
### <a name="remarks"></a>Hinweise  
 Ist ein Steuerelement mit gesperrt `AfxOleLockControl`, sodass dynamisch erstellte mit dem Steuerelement verknüpfte Daten im Arbeitsspeicher bleibt. Dies kann Anzeigebereich des Steuerelements erheblich beschleunigt, da das Steuerelement muss nicht erstellt und zerstört jedes Mal, wenn er angezeigt wird. Wenn Sie das Steuerelement löschen möchten, rufen Sie `AfxOleUnlockControl`.  
   
### <a name="example"></a>Beispiel  
 ```cpp
// Unlock control's (Microsoft Calendar Control) class factory.

AfxOleUnlockControl(_T("MSCAL.Calendar"));

```
   
### <a name="requirements"></a>Anforderungen  
 **Header:**<afxwin.h></afxwin.h>  
   
### <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](mfc-macros-and-globals.md)  
 [AfxOleLockControl](#afxolelockcontrol)


