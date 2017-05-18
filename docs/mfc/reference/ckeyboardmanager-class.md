---
title: Klasse CKeyboardManager | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CKeyboardManager
- AFXKEYBOARDMANAGER/CKeyboardManager
- AFXKEYBOARDMANAGER/CKeyboardManager::CKeyboardManager
- AFXKEYBOARDMANAGER/CKeyboardManager::CleanUp
- AFXKEYBOARDMANAGER/CKeyboardManager::FindDefaultAccelerator
- AFXKEYBOARDMANAGER/CKeyboardManager::IsKeyHandled
- AFXKEYBOARDMANAGER/CKeyboardManager::IsKeyPrintable
- AFXKEYBOARDMANAGER/CKeyboardManager::IsShowAllAccelerators
- AFXKEYBOARDMANAGER/CKeyboardManager::LoadState
- AFXKEYBOARDMANAGER/CKeyboardManager::ResetAll
- AFXKEYBOARDMANAGER/CKeyboardManager::SaveState
- AFXKEYBOARDMANAGER/CKeyboardManager::ShowAllAccelerators
- AFXKEYBOARDMANAGER/CKeyboardManager::TranslateCharToUpper
- AFXKEYBOARDMANAGER/CKeyboardManager::UpdateAccelTable
dev_langs:
- C++
helpviewer_keywords:
- CKeyboardManager class
ms.assetid: 4809ece6-89df-4479-8b53-9bf476ee107b
caps.latest.revision: 33
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: bbe12d2bf4af0008233df25e09f09008c402ee7f
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="ckeyboardmanager-class"></a>CKeyboardManager-Klasse
Verwaltet Tastenkombinationstabellen für das Hauptrahmenfenster und die untergeordneten Rahmenfenster.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CKeyboardManager : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|||  
|-|-|  
|Name|Beschreibung|  
|[CKeyboardManager::CKeyboardManager](#ckeyboardmanager)|Erstellt ein `CKeyboardManager`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|||  
|-|-|  
|Name|Beschreibung|  
|[CKeyboardManager::CleanUp](#cleanup)|Löscht die tastenkombinationstabellen.|  
|[CKeyboardManager::FindDefaultAccelerator](#finddefaultaccelerator)|Ruft die Standardtastenkombination für den angegebenen Befehl und ein Fenster ab.|  
|[CKeyboardManager::IsKeyHandled](#iskeyhandled)|Bestimmt, ob ein Schlüssel von der Zugriffstastentabelle behandelt wird.|  
|[CKeyboardManager::IsKeyPrintable](#iskeyprintable)|Gibt an, ob ein Zeichen druckbaren ist.|  
|[CKeyboardManager::IsShowAllAccelerators](#isshowallaccelerators)|Gibt an, ob Menüs alle Tastenkombinationen für einen Befehl oder nur die Standardtastenkombination angezeigt.|  
|[CKeyboardManager::LoadState](#loadstate)|Lädt die tastenkombinationstabellen aus der Windows-Registrierung.|  
|[CKeyboardManager::ResetAll](#resetall)|Lädt die tastenkombinationstabellen aus der Anwendungsressource erneut.|  
|[CKeyboardManager::SaveState](#savestate)|Speichert die Verknüpfung wichtige Tabellen in der Windows-Registrierung.|  
|[CKeyboardManager::ShowAllAccelerators](#showallaccelerators)|Gibt an, ob das Framework alle Tastenkombinationen für alle Befehle, oder für jeden Befehl einer einzelnen Tastenkombination angezeigt. Diese Methode wirkt sich nicht auf Befehle aus, die nur eine Tastenkombination zugeordnet haben.|  
|[CKeyboardManager::TranslateCharToUpper](#translatechartoupper)|Konvertiert ein Zeichen in der oberen registrieren.|  
|[CKeyboardManager::UpdateAccelTable](#updateacceltable)|Eine wichtige Verknüpfung-Tabelle aktualisiert mit einer neuen Verknüpfung Schlüsseltabelle.|  
  
## <a name="remarks"></a>Hinweise  
 Die Member dieser Klasse können Sie speichern und tastenkombinationstabellen zur Windows-Registrierung zu laden, verwenden Sie eine Vorlage, um die wichtige Verknüpfung-Tabellen zu aktualisieren, und suchen die Standard-Tastenkombination für einen Befehl in einem Rahmenfenster. Darüber hinaus die `CKeyboardManager` Objekt können Sie steuern, wie die Tastenkombinationen, die dem Benutzer angezeigt werden.  
  
 Erstellen Sie keine `CKeyboardManager` Objekt manuell. Es wird automatisch vom Framework der Anwendung erstellt werden. Sie sollten jedoch aufrufen [CWinAppEx::InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager) während der Initialisierung der Anwendung. Rufen Sie zum Abrufen eines Zeigers auf die Tastatur-Manager für Ihre Anwendung [CWinAppEx::GetKeyboardManager](../../mfc/reference/cwinappex-class.md#getkeyboardmanager).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Abrufen von eines Zeigers auf eine `CKeyboardManager` -Objekt aus einer `CWinAppEx` -Klasse, und alle Befehle im Menü zugeordneten Tastenkombinationen anzeigen. Dieser Codeausschnitt ist Teil der [benutzerdefinierte Seiten Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_CustomPages&5;](../../mfc/reference/codesnippet/cpp/ckeyboardmanager-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxkeyboardmanager.h  
  
##  <a name="ckeyboardmanager"></a>CKeyboardManager::CKeyboardManager  
 Erstellt ein `CKeyboardManager`-Objekt.  
  
```  
CKeyboardManager();
```  
  
### <a name="remarks"></a>Hinweise  
 In den meisten Fällen Sie müssen nicht zum Erstellen einer `CKeyboardManager` direkt. Standardmäßig erstellt das Framework für Sie. Um einen Zeiger auf die `CKeyboardManager`, rufen Sie [CWinAppEx::GetKeyboardManager](../../mfc/reference/cwinappex-class.md#getkeyboardmanager). Wenn Sie eine manuell erstellen, müssen Sie es mit der Methode initialisieren [CWinAppEx::InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager).  
  
##  <a name="cleanup"></a>CKeyboardManager::CleanUp  
 Frei der `CKeyboardManager` Ressourcen und löscht alle Schlüssel Kontextmenü-Zuordnungen.  
  
```  
static void CleanUp();
```  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu Tastenkombinationen finden Sie unter [Anpassen von Tastatur und Maus](../../mfc/keyboard-and-mouse-customization.md).  
  
 Sie müssen keinen Aufruf dieser Funktion, wenn die Anwendung beendet wird, da das Framework automatisch beim Beenden der Anwendung aufgerufen wird.  
  
##  <a name="finddefaultaccelerator"></a>CKeyboardManager::FindDefaultAccelerator  
 Ruft die Standardtastenkombination für den angegebenen Befehl und ein Fenster ab.  
  
```  
static BOOL FindDefaultAccelerator(
    UINT uiCmd,  
    CString& str,  
    CFrameWnd* pWndFrame,  
    BOOL bIsDefaultFrame);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmd`  
 Die Befehls-ID.  
  
 [out] `str`  
 Ein Verweis auf ein `CString`-Objekt.  
  
 [in] `pWndFrame`  
 Ein Zeiger auf ein Rahmenfenster.  
  
 [in] `bIsDefaultFrame`  
 Gibt an, ob das Rahmenfenster das Standard-Rahmenfenster.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Verknüpfung gefunden wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sucht den angegebenen Befehl `uiCmd` und ruft die Standard-Taste. Die Methode nimmt die Zeichenfolge, die diese Tastenkombination zugeordnet und schreibt den Wert der `str` Parameter.  
  
##  <a name="iskeyhandled"></a>CKeyboardManager::IsKeyHandled  
 Bestimmt, ob der angegebene Schlüssel behandelt die [CKeyboardManager Klasse](../../mfc/reference/ckeyboardmanager-class.md).  
  
```  
static BOOL __stdcall IsKeyHandled(
    WORD nKey,  
    BYTE fVirt,  
    CFrameWnd* pWndFrame,  
    BOOL bIsDefaultFrame);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `nKey`|Der zu überprüfende Schlüssel.|  
|[in] `fVirt`|Gibt das Verhalten der Tastenkombination. Eine Liste der möglichen Werte finden Sie unter [ZUGRIFFSTASTE Struktur](http://msdn.microsoft.com/library/windows/desktop/ms646340).|  
|[in] `pWndFrame`|Ein Rahmenfenster. Diese Methode bestimmt, ob eine Tastenkombination in diesem Frame behandelt wird.|  
|[in] `bIsDefaultFrame`|Ein boolescher Parameter, der angibt, ob `pWndFrame` ist das Standard-Rahmenfenster.|  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Tastenkombination behandelt wird. `FALSE`Wenn der Schlüssel nicht behandelt wird oder wenn `pWndFrame` ist `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Der Eingabeparameter müssen den Eintrag in der Zugriffstastentabelle sowohl für entsprechen `nKey` und `fVirt` zu bestimmen, ob eine Tastenkombination in behandelt wird `pWndFrame`.  
  
##  <a name="iskeyprintable"></a>CKeyboardManager::IsKeyPrintable  
 Gibt an, ob ein Zeichen druckbaren ist.  
  
```  
static BOOL __stdcall IsKeyPrintable(const UINT nChar);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `nChar`|Das Zeichen, das diese Methode überprüft.|  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn das Zeichen druckbaren ist,&0;, ist er nicht.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode schlägt fehl, wenn ein Aufruf von [GetKeyboardState](http://msdn.microsoft.com/library/windows/desktop/ms646299) ein Fehler auftritt.  
  
##  <a name="isshowallaccelerators"></a>CKeyboardManager::IsShowAllAccelerators  
 Gibt an, ob alle Befehle im Menü zugeordneten Tastenkombinationen oder nur die Standardtastenkombinationen Menüs angezeigt werden.  
  
```  
static BOOL IsShowAllAccelerators();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Anwendung alle Tastenkombinationen für Befehle im Menü aufgelistet; 0, wenn die Anwendung nur die Standardtastenkombinationen zeigt.  
  
### <a name="remarks"></a>Hinweise  
 Die Anwendung führt die Tastenkombinationen für Befehle im Menü in der Menüleiste. Verwenden Sie die Funktion [CKeyboardManager::ShowAllAccelerators](#showallaccelerators) steuern, ob die Anwendung listet alle Tastenkombinationen oder nur die Standardtastenkombinationen.  
  
##  <a name="loadstate"></a>CKeyboardManager::LoadState  
 Lädt die tastenkombinationstabellen aus der Windows-Registrierung.  
  
```  
BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,  
    CFrameWnd* pDefaultFrame = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszProfileName`  
 Im Registrierungspfad befinden, in denen `CKeyboardManager` gespeichert.  
  
 [in] `pDefaultFrame`  
 Ein Zeiger auf ein Rahmenfenster als Standardfenster verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Zustand erfolgreich geladen oder 0 ist.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die `lpszProfileName` Parameter ist `NULL`, diese Methode prüft den Standardspeicherort für die Registrierung für `CKeyboardManager` Daten. Der Standardspeicherort für die Registrierung wird angegeben, indem die [CWinAppEx Class](../../mfc/reference/cwinappex-class.md). Die Daten müssen zuvor geschrieben werden, mit der Methode [CKeyboardManager::SaveState](#savestate).  
  
 Wenn Sie ein Fenster nicht angeben, wird das Hauptrahmenfenster Ihrer Anwendung verwendet werden.  
  
##  <a name="resetall"></a>CKeyboardManager::ResetAll  
 Lädt die tastenkombinationstabellen aus der Anwendungsressource erneut.  
  
```  
void ResetAll();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion löscht die Tastenkombinationen, gespeichert der `CKeyboardManager` Instanz. Den Status der Manager für die Tastatur die Anwendungsressource wird dann erneut laden.  
  
##  <a name="savestate"></a>CKeyboardManager::SaveState  
 Speichert die Verknüpfung wichtige Tabellen in der Windows-Registrierung.  
  
```  
BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,  
    CFrameWnd* pDefaultFrame = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszProfileName`  
 Der Registrierungspfad zum Speichern der `CKeyboardManager` Zustand.  
  
 [in] `pDefaultFrame`  
 Ein Zeiger auf ein Rahmenfenster, die im Fenster wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn der Zustand der Tastatur-Manager erfolgreich gespeichert wurde oder andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der `lpszProfileName` Parameter ist `NULL`, diese Methode schreibt den `CKeyboardManager` am Standardspeicherort, der anhand des Status der [CWinAppEx Class](../../mfc/reference/cwinappex-class.md). Wenn Sie einen Speicherort angeben, können Sie die Daten, die später mithilfe der-Methode laden [CKeyboardManager::LoadState](#loadstate).  
  
 Wenn Sie ein Fenster nicht angeben, wird das Hauptrahmenfenster als Standardfenster verwendet werden.  
  
##  <a name="showallaccelerators"></a>CKeyboardManager::ShowAllAccelerators  
 Zeigt alle Befehle im Menü zugeordneten Tastenkombinationen.  
  
```  
static void ShowAllAccelerators(
    BOOL bShowAll = TRUE,  
    LPCTSTR lpszDelimiter = _afxDefaultAcceleratorDelimiter);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bShowAll`  
 Wenn `true`, alle Tastenkombinationen angezeigt werden. Wenn `false`, nur die erste Tastenkombination wird angezeigt.  
  
 [in] `lpszDelimiter`  
 Eine Zeichenfolge, die zwischen Tastenkombinationen eingefügt. Dieses Trennzeichen hat keine Auswirkung, wenn nur eine Tastenkombination angezeigt wird.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig verfügt ein Befehl mehr als eine Tastenkombination zugeordnet, wird nur die erste Tastenkombination angezeigt. Mit dieser Funktion können Sie alle zugeordneten alle Befehle Tastenkombinationen aufgeführt.  
  
 Neben den Befehl in der Menüleiste werden die Tastenkombinationen aufgeführt. Die Tastenkombinationen aufgeführt, die Zeichenfolge von bereitgestellten `lpszDelimiter` einzelne Tastenkombinationen zu unterteilen.  
  
##  <a name="translatechartoupper"></a>CKeyboardManager::TranslateCharToUpper  
 Konvertiert ein Zeichen in der oberen registrieren.  
  
```  
static UINT TranslateCharToUpper(const UINT nChar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nChar`  
 Das zu konvertierende Zeichen.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Zeichen, das den oberen Register des Eingabeparameters ist.  
  
##  <a name="updateacceltable"></a>CKeyboardManager::UpdateAccelTable  
 Eine wichtige Verknüpfung-Tabelle aktualisiert mit einer neuen Verknüpfung Schlüsseltabelle.  
  
```  
BOOL UpdateAccelTable(
    CMultiDocTemplate* pTemplate,  
    LPACCEL lpAccel,  
    int nSize,  
    CFrameWnd* pDefaultFrame = NULL);

 
BOOL UpdateAccelTable(
    CMultiDocTemplate* pTemplate,  
    HACCEL hAccelNew,  
    CFrameWnd* pDefaultFrame = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pTemplate`  
 Ein Zeiger auf eine Dokumentvorlage.  
  
 [in] `lpAccel`  
 Ein Zeiger auf die neue Tastenkombination.  
  
 [in] `nSize`  
 Die Größe der neuen Verknüpfung Tabelle.  
  
 [in] `pDefaultFrame`  
 Ein Zeiger auf die Standard-Rahmenfenster.  
  
 [in] `hAccelNew`  
 Ein Handle für die neue Tabelle für die Verknüpfung.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Methode erfolgreich ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion, um die vorhandene Verknüpfung Tabelle neue Tastenkombinationen für mehrere Frames im Fensterobjekte zu ersetzen. Die Funktion empfängt eine Dokumentvorlage als Parameter erhalten Zugriff auf alle Objekte des Frame-Fenster mit der angegebenen Dokumentvorlage verbunden.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx-Klasse](../../mfc/reference/cwinappex-class.md)   
 [CWinAppEx::InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager)   
 [Anpassen von Tastatur und Maus](../../mfc/keyboard-and-mouse-customization.md)




