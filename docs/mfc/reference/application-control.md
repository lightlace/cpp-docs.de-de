---
title: Anwendungssteuerelement | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
translationtype: Machine Translation
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 81eb0bcdd8c9d154f62635e7f306cefcf7a15c1b
ms.lasthandoff: 02/24/2017

---
# <a name="application-control"></a>Anwendungssteuerelement
OLE erfordert erhebliche Kontrolle über die Anwendung und ihre Objekte. Die OLE-System-DLLs muss Lage starten und Applikationen automatisch freigeben, koordinieren ihre Erzeugung und Änderung von Objekten usw. sein. Die Funktionen in diesem Thema werden diese Anforderungen erfüllen. Neben der durch die OLE-System-DLLs aufgerufen wird, müssen diese Funktionen manchmal von Clientanwendungen sowie aufgerufen werden.  
  
### <a name="application-control"></a>Anwendungssteuerelement  
  
|||  
|-|-|  
|[AfxOleCanExitApp](#afxolecanexitapp)|Gibt an, ob die Anwendung beenden kann.|  
|[AfxOleGetMessageFilter](#afxolegetmessagefilter)|Ruft die aktuelle Nachricht Anwendungsfilter ab.|  
|[AfxOleGetUserCtrl](#afxolegetuserctrl)|Ruft das aktuelle Benutzersteuerelement Kennzeichen ab.|  
|[AfxOleSetUserCtrl](#afxolesetuserctrl)|Aktiviert oder deaktiviert die Benutzersteuerelement Flag.|  
|[AfxOleLockApp](#afxolelockapp)|Erhöht die Framework globalen Zähler für die Anzahl von aktiven Objekten in einer Anwendung.|  
|[AfxOleUnlockApp](#afxoleunlockapp)|Verringert das Framework die Anzahl von aktiven Objekten in einer Anwendung.|  
|[AfxOleRegisterServerClass](#afxoleregisterserverclass)|Registriert einen Server in der Registrierung des OLE-Systems.|  
|[AfxOleSetEditMenu](#afxoleseteditmenu)|Implementiert die Benutzeroberfläche für die *Typename* Objekt-Befehl.|  
  
##  <a name="a-nameafxolecanexitappa--afxolecanexitapp"></a><a name="afxolecanexitapp"></a>AfxOleCanExitApp  
 Gibt an, ob die Anwendung beenden kann.  
  
```   
BOOL AFXAPI AfxOleCanExitApp(); 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Anwendung beendet werden kann; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Eine Anwendung sollte nicht beendet werden, wenn ausstehende Verweise auf die Objekte vorhanden sind. Die globalen Funktionen `AfxOleLockApp` und `AfxOleUnlockApp` Inkrementieren und Dekrementieren, einen Indikator von Verweisen auf Objekte die Anwendung. Die Anwendung sollte nicht beendet, wenn dieser Wert ungleich NULL ist. Wenn der Zähler ungleich NULL ist, wird im Hauptfenster der Anwendung (nicht zerstört) ausgeblendet, wenn der Benutzer schließen aus dem Systemmenü oder Beenden im Menü Datei. Das Framework ruft diese Funktion **CFrameWnd::OnClose**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCAutomation&#2;](../../mfc/codesnippet/cpp/application-control_1.cpp)]  

## <a name="requirements"></a>Anforderungen  
 **Header**: afxdisp.h 

##  <a name="a-nameafxolegetmessagefiltera--afxolegetmessagefilter"></a><a name="afxolegetmessagefilter"></a>AfxOleGetMessageFilter  
 Ruft die aktuelle Nachricht Anwendungsfilter ab.  
  
```   
COleMessageFilter* AFXAPI  AfxOleGetMessageFilter(); 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den aktuellen Nachrichtenfilter.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion für den Zugriff auf die aktuelle `COleMessageFilter`-Objekt abgeleitet, wie Sie aufrufen `AfxGetApp` Zugriff auf das Anwendungsobjekt der aktuellen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCAutomation&3;](../../mfc/codesnippet/cpp/application-control_2.cpp)]  
  
 [!code-cpp[NVC_MFCAutomation&4;](../../mfc/codesnippet/cpp/application-control_3.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header**: afxwin.h 

##  <a name="a-nameafxolegetuserctrla--afxolegetuserctrl"></a><a name="afxolegetuserctrl"></a>AfxOleGetUserCtrl  
 Ruft das aktuelle Benutzersteuerelement Kennzeichen ab.  
  
```   
BOOL  AFXAPI AfxOleGetUserCtrl(); 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Benutzer im Steuerelement der Anwendung ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Der Benutzer ist im Steuerelement der Anwendung, wenn der Benutzer explizit geöffnet oder erstellt ein neues Dokument. Der Benutzer ist auch im Steuerelement, wenn die Anwendung durch die OLE-System-DLLs nicht gestartet wurde – mit anderen Worten, wenn der Benutzer die Anwendung mit der System-Shell gestartet.  

### <a name="requirements"></a>Anforderungen  
 **Header**: afxdisp.h

##  <a name="a-nameafxolesetuserctrla--afxolesetuserctrl"></a><a name="afxolesetuserctrl"></a>AfxOleSetUserCtrl  
 Aktiviert oder deaktiviert die Benutzersteuerelement-Flag, das in der Referenz für erklärt `AfxOleGetUserCtrl`.  
  
```  
void  AFXAPI AfxOleSetUserCtrl(BOOL bUserCtrl); 
```  
  
### <a name="parameters"></a>Parameter  
 *bUserCtrl*  
 Gibt an, ob das Benutzersteuerelement Flag festgelegt oder deaktiviert werden.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Funktion, wenn der Benutzer erstellt oder ein Dokument lädt, jedoch nicht, wenn ein Dokument geladen oder über eine indirekte Aktion, z. B. das Laden eines eingebetteten Objekts in eine Steuerelementcontainer-Anwendung erstellt.  
  
 Rufen Sie diese Funktion, wenn Sie andere Aktionen in der Anwendung den Benutzer im Steuerelement der Anwendung eingefügt werden soll.  

### <a name="requirements"></a>Anforderungen  
 **Header**: afxdisp.h

##  <a name="a-nameafxolelockappa--afxolelockapp"></a><a name="afxolelockapp"></a>AfxOleLockApp  
 Erhöht die Framework globalen Zähler für die Anzahl von aktiven Objekten in der Anwendung.  
  
```   
void  AFXAPI  AfxOleLockApp(); 
```  
  
### <a name="remarks"></a>Hinweise  
 Das Framework wird die Anzahl der Objekte in einer Anwendung aktiv gehalten. Die `AfxOleLockApp` und `AfxOleUnlockApp` Funktionen bzw. Inkrement- und Dekrement-dieser Zähler.  
  
 Wenn der Benutzer versucht, eine Anwendung zu schließen, die aktive Objekte – eine Anwendung, für die die Anzahl der aktiven Objekte ungleich NULL ist – das Framework wird die Anwendung aus Sicht der Benutzer nicht vollständig heruntergefahren, sondern ausgeblendet. Die `AfxOleCanExitApp` Funktion gibt an, ob die Anwendung beenden kann.  
  
 Rufen Sie `AfxOleLockApp` aller Objekte, die OLE-Schnittstellen verfügbar macht, wäre es nicht wünschenswert, dass das Objekt gelöscht werden, während Sie von einer Clientanwendung verwendet wird. Rufen Sie außerdem `AfxOleUnlockApp` im Destruktor für ein beliebiges Objekt, das Aufrufe `AfxOleLockApp` im Konstruktor. In der Standardeinstellung `COleDocument` (und abgeleitete Klassen) automatisch sperren und entsperren Sie die Anwendung.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCAutomation&5;](../../mfc/codesnippet/cpp/application-control_4.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header**: afxdisp.h

##  <a name="a-nameafxoleunlockappa--afxoleunlockapp"></a><a name="afxoleunlockapp"></a>AfxOleUnlockApp  
 Dekrementiert den Wert des Frameworks Anzahl von aktiven Objekten in der Anwendung.  
  
```   
void AFXAPI AfxOleUnlockApp(); 
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter `AfxOleLockApp` Weitere Informationen.  
  
 Wenn die Anzahl der aktiven Objekte den Wert Null erreicht **AfxOleOnReleaseAllObjects** aufgerufen wird.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [AfxOleLockApp](#afxolelockapp).  

### <a name="requirements"></a>Anforderungen  
 **Header**: afxdisp.h  

##  <a name="a-nameafxoleregisterserverclassa--afxoleregisterserverclass"></a><a name="afxoleregisterserverclass"></a>AfxOleRegisterServerClass  
 Mit dieser Funktion können Sie zum Registrieren des Servers in der Registrierung des OLE-Systems.  
  
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
 Verweis auf den Server OLE-Klassen-ID  
  
 `lpszClassName`  
 Ein Zeiger auf eine Zeichenfolge, die den Klassennamen von Objekten des Servers enthält.  
  
 *lpszShortTypeName*  
 Zeiger auf eine Zeichenfolge mit den kurzen Namen des Objekttyps des Servers, z. B. "Diagramm".  
  
 *lpszLongTypeName*  
 Zeiger auf eine Zeichenfolge mit den langen Namen des Objekttyps des Servers, z. B. "Microsoft Excel 5.0-Diagrammen.  
  
 `nAppType`  
 Ein Wert aus der **OLE_APPTYPE** -Enumeration und gibt den Typ des OLE-Anwendung. Mögliche Werte sind die folgenden:  
  
- `OAT_INPLACE_SERVER`Server hat vollständige Server-Benutzeroberfläche.  
  
- `OAT_SERVER`Server unterstützt nur einbetten.  
  
- `OAT_CONTAINER`Container unterstützt Links zu einbettungen.  
  
- `OAT_DISPATCH_OBJECT``IDispatch`-fähigen Objekt.  
  
 `rglpszRegister`  
 Ein Array von Zeigern auf Zeichenfolgen, die die Schlüssel und Werte, die OLE-System-Registrierung hinzugefügt werden, wenn keine vorhandenen Werte für die Schlüssel gefunden werden.  
  
 `rglpszOverwrite`  
 Ein Array von Zeigern auf Zeichenfolgen, die die Schlüssel und Werte für die OLE-System-Registrierung hinzugefügt werden, wenn die Registrierung vorhandene Werte für den angegebenen Schlüssel enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Klasse des Servers erfolgreich registriert wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die meisten Programme können **COleTemplateServer::Register** Dokumenttypen für die Anwendung zu registrieren. Wenn Ihre Anwendung Registrierung Format nicht der normale Muster passt, können Sie `AfxOleRegisterServerClass` zu steuern.  
  
 Die Registrierung besteht aus einem Satz von Schlüsseln und Werten. Die `rglpszRegister` und `rglpszOverwrite` Argumente sind Arrays von Zeigern auf Zeichenfolgen, bestehend aus einem Schlüssel und Wert durch voneinander getrennte ein **NULL** Zeichen ( `'\0'`). Jede dieser Zeichenfolgen können ersetzbare Parameter, dessen stellen wurde, die Zeichenfolgen markiert `%1` über `%5`.  
  
 Die Symbole werden wie folgt ausgefüllt:  
  
|Symbol|Wert|  
|------------|-----------|  
|%1|Klassen-ID als Zeichenfolge formatiert.|  
|%2|Klassenname|  
|%3|Pfad zur ausführbaren Datei|  
|%4|Kurze Typname|  
|%5|Lange Namen|  

### <a name="requirements"></a>Anforderungen  
 **Header**: afxdisp.h

##  <a name="a-nameafxoleseteditmenua--afxoleseteditmenu"></a><a name="afxoleseteditmenu"></a>AfxOleSetEditMenu  
 Implementiert die Benutzeroberfläche für die *Typename* Objekt-Befehl.  
  
```   
void  AFXAPI  AfxOleSetEditMenu(
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
 Die Befehls-ID, die der letzten Verb entspricht.  
  
 *nIDConvert*  
 Die ID für das Menüelement konvertieren.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Server nur ein primäres Verb erkennt, wird das Menüelement "Verb *Typename* Objekt" und der `nIDVerbMin` -Befehl gesendet wird, wenn der Benutzer den Befehl auswählt. Wenn der Server mehrere Verben erkennt, wird das Menüelement " *Typename* Objekt" und ein Untermenü mit alle Verben angezeigt wird, wenn der Benutzer den Befehl auswählt. Wenn der Benutzer ein Verb im Untermenü `nIDVerbMin` wird gesendet, wenn das erste Verb ausgewählt wird, `nIDVerbMin` + 1 wird gesendet, wenn das zweite Verb ausgewählten usw. ist. Die Standardeinstellung `COleDocument` Implementierung dieser Funktion automatisch behandelt.  
  
 Sie benötigen die folgende Anweisung in der Client Anwendung Ressourcenskript (. RC)-Datei:  
  
 **#include \<afxolecl.rc >**  

### <a name="requirements"></a>Anforderungen  
 **Header**: afxole.h 

## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)

