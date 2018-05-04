---
title: -CLRSUPPORTLASTERROR (Preserve letzten Fehlercode für PInvoke-Aufrufe) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /CLRSUPPORTLASTERROR
dev_langs:
- C++
helpviewer_keywords:
- /CLRSUPPORTLASTERROR linker option
- -CLRSUPPORTLASTERROR linker option
ms.assetid: b7057990-4154-4b1d-9fc9-6236f7be7575
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 297414aa71e9d871da795c2ffe567573237c7e0e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="clrsupportlasterror-preserve-last-error-code-for-pinvoke-calls"></a>/CLRSUPPORTLASTERROR (Letzten Fehlercode für PInvoke-Aufrufe beibehalten)
**/ CLRSUPPORTLASTERROR**, die ist standardmäßig aktiviert, behält der letzte Fehlercode von Funktionen aufgerufen werden, mithilfe der P/Invoke-Mechanismus, dadurch können Sie Code aufrufen systemeigene Funktionen in DLLS kompiliert mit **"/ CLR"**.  
  
## <a name="syntax"></a>Syntax  
  
```  
/CLRSUPPORTLASTERROR{:NO | SYSTEMDLL}  
```  
  
## <a name="remarks"></a>Hinweise  
 Beibehalten von den letzten Fehlercode bedeutet eine Abnahme der Leistung.  Wenn Sie nicht, die Leistungseinbußen bei der Beibehaltung des letzten Fehlercodes erforderlich war möchten, eine Verknüpfung mit **/CLRSUPPORTLASTERROR:NO**.  
  
 Sie können die Auswirkungen auf die Leistung minimieren, durch eine Verknüpfung mit **/CLRSUPPORTLASTERROR:SYSTEMDLL**, die nur den letzten Fehlercode für Funktionen beibehalten, im System-DLLs.  Eine DLL des Mailsystems ist als eine der folgenden definiert:  
  
|||||  
|-|-|-|-|  
|ACLUI. DLL|ACTIVEDS. DLL|ADPTIF. DLL|ADVAPI32. DLL|  
|ASYCFILT. DLL|AUTHZ. DLL|AVICAP32. DLL|AVIFIL32. DLL|  
|CAB-DATEI. DLL|CLUSAPI. DLL|COMCTL32. DLL|COMDLG32. DLL|  
|COMSVCS. DLL|CREDUI. DLL|CRYPT32. DLL|CRYPTNET. DLL|  
|CRYPTUI. DLL|D3D8THK. DLL|DBGENG. DLL|DBGHELP. DLL|  
|DCIMAN32. DLL|DNSAPI. DLL|DSPROP. DLL|DSUIEXT. DLL|  
|GDI32. DLL|GLU32. DLL|HLINK. DLL|ICM32. DLL|  
|IMAGEHLP. DLL|IMM32. DLL|IPHLPAPI. DLL|IPROP. DLL|  
|KERNEL32. DLL|KSUSER. DLL|LOADPERF. DLL|LZ32. DLL|  
|MAPI32. DLL|MGMTAPI. DLL|MOBSYNC. DLL|MPR. DLL|  
|MPRAPI. DLL|MQRT. DLL|MSACM32. DLL|MSCMS. DLL|  
|MSI-DATEI. DLL|MSIMG32. DLL|MSRATING. DLL|MSTASK. DLL|  
|MSVFW32. DLL|MSWSOCK. DLL|MTXEX. DLL|NDDEAPI. DLL|  
|NETAPI32. DLL|NPPTOOLS. DLL|NTDSAPI. DLL|NTDSBCLI. DLL|  
|NTMSAPI. DLL|ODBC32. DLL|ODBCBCP. DLL|OLE32. DLL|  
|OLEACC. DLL|OLEAUT32. DLL|OLEDLG. DLL|OPENGL32. DLL|  
|PDH. DLL|POWRPROF. DLL|QOSNAME. DLL|ABGEFRAGT WERDEN. DLL|  
|RASAPI32. DLL|RASDLG. DLL|RASSAPI. DLL|RESUTILS. DLL|  
|RICHED20. DLL|RPCNS4. DLL|RPCRT4. DLL|RTM. DLL|  
|RTUTILS. DLL|SCARDDLG. DLL|SECUR32. DLL|SENSAPI. DLL|  
|SETUPAPI. DLL|SFC. DLL|SHELL32. DLL|SHFOLDER. DLL|  
|SETZT. DLL|SISBKUP. DLL|SNMPAPI. DLL|SRCLIENT. DLL|  
|STI UMGEWANDELT WERDEN. DLL|TAPI32. DLL|DATENVERKEHR. DLL|URL. DLL|  
|URLMON. DLL|USER32. DLL|USERENV. DLL|USP10. DLL|  
|UXTHEME. DLL|VDMDBG. DLL|VERSION. DLL|WINFAX. DLL|  
|WINHTTP. DLL|WININET. DLL|WINMM. DLL|WINSCARD. DLL|  
|WINTRUST. DLL|WLDAP32. DLL|WOW32. DLL|WS2_32.DLL|  
|WSNMP32. DLL|WSOCK32.DLL|WTSAPI32. DLL|XOLEHLP. DLL|  
  
> [!NOTE]
>  Den letzten Fehler beibehalten wird für nicht verwaltete Funktionen, die von CLR-Code im selben Modul genutzt werden, nicht unterstützt.  
  
-   Weitere Informationen finden Sie unter [/clr (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf die **Linker** Ordner.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .  
  
4.  Geben Sie die Option in der **Zusatzoptionen** Feld.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel definiert eine systemeigene DLL mit einer exportierten Funktion, die letzten Fehler ändert.  
  
```  
// CLRSUPPORTLASTERROR_dll.cpp  
// compile with: /LD  
#include <windows.h>  
#include <math.h>  
  
#pragma unmanaged  
__declspec(dllexport) double MySqrt(__int64 n) {  
   SetLastError(DWORD(-1));  
   return sqrt(double(n));  
}  
```  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel verwendet die DLL, und die Verwendung **/CLRSUPPORTLASTERROR**.  
  
```  
// CLRSUPPORTLASTERROR_client.cpp  
// compile with: /clr CLRSUPPORTLASTERROR_dll.lib /link /clrsupportlasterror:systemdll  
// processor: x86  
#include <windows.h>  
#include <wininet.h>  
#include <stdio.h>  
#include <math.h>  
  
#pragma comment(lib, "wininet.lib")  
  
double MySqrt(__int64 n);  
  
#pragma managed  
int main() {  
   double   d = 0.0;  
   __int64 n = 65;  
   HANDLE  hGroup = NULL;  
   GROUPID groupID;  
   DWORD   dwSet = 127, dwGet = 37;  
  
   SetLastError(dwSet);  
   d = MySqrt(n);  
   dwGet = GetLastError();  
  
   if (dwGet == DWORD(-1))  
      printf_s("GetLastError for application call succeeded (%d).\n",  
             dwGet);  
   else  
      printf_s("GetLastError for application call failed (%d).\n",  
             dwGet);  
  
   hGroup = FindFirstUrlCacheGroup(0, CACHEGROUP_SEARCH_ALL,  
                           0, 0, &groupID, 0);  
   dwGet = GetLastError();  
   if (dwGet == 183)  
      printf_s("GetLastError for system call succeeded (%d).\n",  
             dwGet);  
   else  
      printf_s("GetLastError for system call failed (%d).\n",  
             dwGet);  
}  
```  
  
```Output  
GetLastError for application call failed (127).  
GetLastError for system call succeeded (183).  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)