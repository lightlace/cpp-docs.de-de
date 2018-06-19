---
title: CKeyboardManager Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CKeyboardManager [MFC], CKeyboardManager
- CKeyboardManager [MFC], CleanUp
- CKeyboardManager [MFC], FindDefaultAccelerator
- CKeyboardManager [MFC], IsKeyHandled
- CKeyboardManager [MFC], IsKeyPrintable
- CKeyboardManager [MFC], IsShowAllAccelerators
- CKeyboardManager [MFC], LoadState
- CKeyboardManager [MFC], ResetAll
- CKeyboardManager [MFC], SaveState
- CKeyboardManager [MFC], ShowAllAccelerators
- CKeyboardManager [MFC], TranslateCharToUpper
- CKeyboardManager [MFC], UpdateAccelTable
ms.assetid: 4809ece6-89df-4479-8b53-9bf476ee107b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1b9d4aace502310836429ec8f8f9db74d7cf17ff
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33369101"
---
# <a name="ckeyboardmanager-class"></a>CKeyboardManager-Klasse
Verwaltet Tastenkombinationstabellen für das Hauptrahmenfenster und die untergeordneten Rahmenfenster.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CKeyboardManager : public CObject  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|||  
|-|-|  
|Name|Beschreibung|  
|[CKeyboardManager::CKeyboardManager](#ckeyboardmanager)|Erstellt ein `CKeyboardManager`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|||  
|-|-|  
|Name|Beschreibung|  
|[CKeyboardManager::CleanUp](#cleanup)|Löscht die tastenkombinationstabellen an.|  
|[CKeyboardManager::FindDefaultAccelerator](#finddefaultaccelerator)|Ruft die standardmäßige Tastenkombination für den angegebenen Befehl und Fenster ab.|  
|[CKeyboardManager::IsKeyHandled](#iskeyhandled)|Bestimmt, ob ein Schlüssel durch die Zugriffstastentabelle behandelt wird.|  
|[CKeyboardManager::IsKeyPrintable](#iskeyprintable)|Gibt an, ob ein Zeichen ist, die gedruckt werden können.|  
|[CKeyboardManager::IsShowAllAccelerators](#isshowallaccelerators)|Gibt an, ob alle Tastenkombinationen für einen Befehl oder nur die standardmäßige Tastenkombination Menüs angezeigt werden.|  
|[CKeyboardManager::LoadState](#loadstate)|Lädt die tastenkombinationstabellen aus der Windows-Registrierung.|  
|[CKeyboardManager::ResetAll](#resetall)|Lädt die tastenkombinationstabellen aus der Anwendungsressource erneut.|  
|[CKeyboardManager::SaveState](#savestate)|Speichert die Verknüpfung Key Tabellen an der Windows-Registrierung.|  
|[CKeyboardManager::ShowAllAccelerators](#showallaccelerators)|Gibt an, ob das Framework die Tastenkombinationen für alle Befehle oder einer einzelnen Tastenkombination für jedem Befehl angezeigt wird. Diese Methode wirkt sich nicht auf Befehle aus, die nur einen zugeordneten Tastenkombination verfügen.|  
|[CKeyboardManager::TranslateCharToUpper](#translatechartoupper)|Konvertiert ein Zeichen in der oberen registrieren.|  
|[CKeyboardManager::UpdateAccelTable](#updateacceltable)|Tabellenform Verknüpfung aktualisiert mit einer neuen Verknüpfung-Key-Tabelle.|  
  
## <a name="remarks"></a>Hinweise  
 Die Member dieser Klasse ermöglichen es Ihnen, speichern und Laden tastenkombinationstabellen zur Windows-Registrierung, anhand einer Vorlage um die Abkürzung Key Tabellen zu aktualisieren, und suchen die standardmäßige Tastenkombination für einen Befehl in einem Rahmenfenster. Darüber hinaus die `CKeyboardManager` Objekt können Sie steuern, wie die Tastenkombinationen für den Benutzer angezeigt werden.  
  
 Sie sollten keine erstellen eine `CKeyboardManager` Objekt manuell. Es wird automatisch durch das Framework der Anwendung erstellt werden. Sie sollten jedoch aufrufen [CWinAppEx::InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager) während der Initialisierung der Anwendung. Rufen Sie zum Abrufen eines Zeigers auf die Tastatur-Manager für Ihre Anwendung [CWinAppEx::GetKeyboardManager](../../mfc/reference/cwinappex-class.md#getkeyboardmanager).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie einen Zeiger zum Abrufen einer `CKeyboardManager` -Objekt aus einer `CWinAppEx` Klasse sowie zum Anzeigen aller Tastenkombinationen, die Befehle im Menü zugeordnet. Dieser Codeausschnitt ist Teil der [benutzerdefinierte Seiten Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_CustomPages#5](../../mfc/reference/codesnippet/cpp/ckeyboardmanager-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxkeyboardmanager.h  
  
##  <a name="ckeyboardmanager"></a>  CKeyboardManager::CKeyboardManager  
 Erstellt ein `CKeyboardManager`-Objekt.  
  
```  
CKeyboardManager();
```  
  
### <a name="remarks"></a>Hinweise  
 In den meisten Fällen Sie keine zum Erstellen einer `CKeyboardManager` direkt. Standardmäßig erstellt das Framework einer für Sie. Um einen Zeiger auf die `CKeyboardManager`, rufen Sie [CWinAppEx::GetKeyboardManager](../../mfc/reference/cwinappex-class.md#getkeyboardmanager). Wenn Sie eine manuell erstellen, müssen Sie es mit der Methode initialisieren [CWinAppEx::InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager).  
  
##  <a name="cleanup"></a>  CKeyboardManager::CleanUp  
 Gibt die `CKeyboardManager` Ressourcen und löscht alle Schlüssel Verknüpfung-Zuordnungen.  
  
```  
static void CleanUp();
```  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu Tastenkombinationen, finden Sie unter [Anpassen von Tastatur und Maus](../../mfc/keyboard-and-mouse-customization.md).  
  
 Sie müssen nicht diese Funktion aufgerufen wird, wenn die Anwendung beendet wird, da das Framework sie beim Beenden der Anwendung automatisch aufruft.  
  
##  <a name="finddefaultaccelerator"></a>  CKeyboardManager::FindDefaultAccelerator  
 Ruft die standardmäßige Tastenkombination für den angegebenen Befehl und Fenster ab.  
  
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
 Gibt an, ob das Rahmenfenster der Standard-Rahmenfenster ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Verknüpfung gefunden wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sucht den vom angegebenen Befehl `uiCmd` und ruft die standardmäßige Tastenkombination ab. Die Methode nimmt die Zeichenfolge, die diese Tastenkombination zugeordnet, und schreibt den Wert der `str` Parameter.  
  
##  <a name="iskeyhandled"></a>  CKeyboardManager::IsKeyHandled  
 Bestimmt, ob der angegebene Schlüssel vom behandelt wird die [CKeyboardManager Klasse](../../mfc/reference/ckeyboardmanager-class.md).  
  
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
|[in] `fVirt`|Gibt das Verhalten der Tastenkombination. Eine Liste der möglichen Werte finden Sie unter [ACCELERATION Struktur](http://msdn.microsoft.com/library/windows/desktop/ms646340).|  
|[in] `pWndFrame`|Einem Rahmenfenster. Diese Methode bestimmt, ob eine Tastenkombination in diesem Frame behandelt wird.|  
|[in] `bIsDefaultFrame`|Ein boolescher Parameter, der angibt, ob `pWndFrame` ist das Standard-Rahmenfenster.|  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn die Tastenkombination behandelt wird. `FALSE` Wenn der Schlüssel nicht behandelt wird oder wenn `pWndFrame` ist `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Der Eingabeparameter müssen den Eintrag in der Zugriffstastentabelle sowohl für entsprechen `nKey` und `fVirt` zu bestimmen, ob eine Tastenkombination im behandelt wird `pWndFrame`.  
  
##  <a name="iskeyprintable"></a>  CKeyboardManager::IsKeyPrintable  
 Gibt an, ob ein Zeichen ist, die gedruckt werden können.  
  
```  
static BOOL __stdcall IsKeyPrintable(const UINT nChar);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `nChar`|Das Zeichen, das diese Methode überprüft.|  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL ist das Zeichen gedruckt werden können, ist er nicht auf NULL.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode schlägt fehl, wenn ein Aufruf von [GetKeyboardState](http://msdn.microsoft.com/library/windows/desktop/ms646299) ein Fehler auftritt.  
  
##  <a name="isshowallaccelerators"></a>  CKeyboardManager::IsShowAllAccelerators  
 Gibt an, ob alle Tastenkombinationen, die Befehle im Menü zugeordnet oder nur die Standardtastenkombinationen Menüs angezeigt werden.  
  
```  
static BOOL IsShowAllAccelerators();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Anwendung die Tastenkombinationen für Befehle im Menü aufgelistet; 0, wenn die Anwendung nur die Standardtastenkombinationen zeigt.  
  
### <a name="remarks"></a>Hinweise  
 Die Anwendung werden die Tastenkombinationen für Befehle in der Menüleiste im Menü aufgelistet. Verwenden Sie die Funktion [CKeyboardManager::ShowAllAccelerators](#showallaccelerators) steuern, ob die Anwendung listet alle Tastenkombinationen oder nur die Standardtastenkombinationen.  
  
##  <a name="loadstate"></a>  CKeyboardManager::LoadState  
 Lädt die tastenkombinationstabellen aus der Windows-Registrierung.  
  
```  
BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,  
    CFrameWnd* pDefaultFrame = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszProfileName`  
 Der Registrierungspfad, in denen `CKeyboardManager` Daten gespeichert ist.  
  
 [in] `pDefaultFrame`  
 Ein Zeiger auf ein Rahmenfenster als Standardfenster verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Zustand erfolgreich geladen oder 0 ist.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die `lpszProfileName` Parameter ist `NULL`, diese Methode überprüft den Standardspeicherort für die Registrierung für `CKeyboardManager` Daten. Der Standardspeicherort für die Registrierung wird angegeben, indem die [CWinAppEx Class](../../mfc/reference/cwinappex-class.md). Die Daten müssen zuvor geschrieben werden, mit der Methode [CKeyboardManager::SaveState](#savestate).  
  
 Wenn Sie ein Standardfenster nicht angeben, wird das Hauptrahmenfenster Ihrer Anwendung verwendet werden.  
  
##  <a name="resetall"></a>  CKeyboardManager::ResetAll  
 Lädt die tastenkombinationstabellen aus der Anwendungsressource erneut.  
  
```  
void ResetAll();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion löscht die Tastenkombinationen, gespeichert der `CKeyboardManager` Instanz. Es wird das den Status der Tastatur-Manager aus der Anwendungsressource dann neu.  
  
##  <a name="savestate"></a>  CKeyboardManager::SaveState  
 Speichert die Verknüpfung Key Tabellen an der Windows-Registrierung.  
  
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
 Wenn die `lpszProfileName` Parameter ist `NULL`, diese Methode schreibt den `CKeyboardManager` Zustands, in der vom angegebenen Standardspeicherort der [CWinAppEx Class](../../mfc/reference/cwinappex-class.md). Wenn Sie einen Speicherort angeben, können Sie die Daten, die später mithilfe der Methode laden [CKeyboardManager::LoadState](#loadstate).  
  
 Wenn Sie ein Standardfenster nicht angeben, wird das Hauptrahmenfenster als Standardfenster verwendet werden.  
  
##  <a name="showallaccelerators"></a>  CKeyboardManager::ShowAllAccelerators  
 Zeigt alle Tastenkombinationen, die Befehle im Menü zugeordnet.  
  
```  
static void ShowAllAccelerators(
    BOOL bShowAll = TRUE,  
    LPCTSTR lpszDelimiter = _afxDefaultAcceleratorDelimiter);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bShowAll`  
 Wenn `true`, alle Tastenkombinationen angezeigt. Wenn `false`, nur die ersten Tastenkombination wird angezeigt.  
  
 [in] `lpszDelimiter`  
 Eine Zeichenfolge, die zwischen Tastenkombinationen eingefügt. Diese Trennzeichen hat keine Auswirkungen, wenn nur eine Tastenkombination angezeigt wird.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig verfügt ein Befehl mehr als eine Tastenkombination zugeordnet, wird nur die erste Tastenkombination angezeigt. Diese Funktion können Sie alle zugeordneten alle Befehle Tastenkombinationen aufgeführt.  
  
 Neben den Befehl in der Menüleiste werden die Tastenkombinationen aufgeführt. Wenn alle Tastenkombinationen angezeigt werden, wird die Zeichenfolge von bereitgestellten `lpszDelimiter` einzelne Tastenkombinationen getrennt wird.  
  
##  <a name="translatechartoupper"></a>  CKeyboardManager::TranslateCharToUpper  
 Konvertiert ein Zeichen in der oberen registrieren.  
  
```  
static UINT TranslateCharToUpper(const UINT nChar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nChar`  
 Das zu konvertierende Zeichen.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Zeichen, das den oberen Register des Eingabeparameters ist.  
  
##  <a name="updateacceltable"></a>  CKeyboardManager::UpdateAccelTable  
 Tabellenform Verknüpfung aktualisiert mit einer neuen Verknüpfung-Key-Tabelle.  
  
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
 Die Größe der neuen Verknüpfung-Tabelle.  
  
 [in] `pDefaultFrame`  
 Ein Zeiger auf das Standard-Rahmenfenster.  
  
 [in] `hAccelNew`  
 Ein Handle für die neue Tabelle für die Verknüpfung.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Methode erfolgreich ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion, um die vorhandene Verknüpfung-Tabelle mit neuen Tastenkombinationen für mehrere Objekte der Frame-Fensters zu ersetzen. Die Funktion empfängt eine Dokumentvorlage als Parameter für den Zugriff auf alle Objekte des Frame-Fensters mit dem angegebenen Dokumentvorlage verbunden zu erhalten.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx-Klasse](../../mfc/reference/cwinappex-class.md)   
 [CWinAppEx::InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager)   
 [Anpassen von Tastatur und Maus](../../mfc/keyboard-and-mouse-customization.md)



