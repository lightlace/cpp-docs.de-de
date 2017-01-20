---
title: "_getdiskfree"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_getdiskfree"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-filesystem-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "getdiskfree"
  - "_getdiskfree"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_diskfree_t-Typ"
  - "_getdiskfree-Funktion"
  - "Datenträgergröße"
  - "diskfree_t-Typ"
  - "getdiskfree-Funktion"
ms.assetid: 47a3f6cf-4816-452a-8f3d-1c3ae02a0f2a
caps.latest.revision: 21
caps.handback.revision: "19"
ms.author: "corob"
manager: "ghogen"
---
# _getdiskfree
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Verwendet Informationen über ein Laufwerk zum Auffüllen einer `_diskfree_t`\-Struktur.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die im [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
unsigned _getdiskfree(  
   unsigned drive,  
   struct _diskfree_t * driveinfo  
);  
```  
  
#### Parameter  
 \[in\] `drive`  
 Das Laufwerk, zu dem Sie Informationen abrufen möchten.  
  
 \[out\] `driveinfo`  
 Eine `_diskfree_t`\-Struktur, die mit Informationen über den Datenträger aufgefüllt wird.  
  
## Rückgabewert  
 Wenn die Funktion erfolgreich ist, ist der Rückgabewert „0“.  Wenn die Funktion fehlerhaft ist, wird der Fehlercode als Rückgabewert ausgegeben.  Der Wert `errno` wird für Fehler festgelegt, die durch das Betriebssystem zurückgegeben werden.  Weitere Informationen über durch `errno` angezeigte Fehlerbedingungen finden Sie unter [errno\-Konstanten](../../c-runtime-library/errno-constants.md).  
  
## Hinweise  
 Die `_diskfree_t`\-Struktur wurde in „Direct.h“ definiert.  
  
```  
struct _diskfree_t {   
   unsigned total_clusters;   
   unsigned avail_clusters;   
   unsigned sectors_per_cluster;   
   unsigned bytes_per_sector;   
};  
```  
  
 Diese Funktion überprüft ihre Parameter.  Wenn der `driveinfo`\-Zeiger `NULL` ist oder wenn `drive` ein ungültiges Laufwerk angibt, ruft diese Funktion einen ungültigen Parameterhandler ab, wie dies unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben wird.  Wenn die weitere Ausführung zugelassen wird, gibt die Funktion `EINVAL` zurück und setzt `errno` auf `EINVAL`.  Der gültige Laufwerksbereich liegt zwischen 0 und 26.  Ein `drive`\-Wert von „0“ gibt das aktuelle Laufwerk an. Danach werden Zahlen Buchstaben des englischen Alphabets zugeordnet, „1“ deutet demnach auf Laufwerk A, „3“ auf Laufwerk C usw. hin.  
  
 `total_clusters`  
 Die Gesamtanzahl der Cluster, die auf dem Laufwerk verwendet werden und verfügbar sind.  
  
 `avail_clusters`  
 Die Anzahl der nicht verwendeten Cluster auf dem Laufwerk.  
  
 `sectors_per_cluster`  
 Die Anzahl der Sektoren in jedem Cluster.  
  
 `bytes_per_sector`  
 Die Größe jedes Sektors in Byte.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_getdiskfree`|\<direct.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
// crt_getdiskfree.c  
// compile with: /c  
#include <windows.h>  
#include <direct.h>  
#include <stdio.h>  
#include <tchar.h>  
  
TCHAR   g_szBorder[] = _T("======================================================================\n");  
TCHAR   g_szTitle1[] = _T("|DRIVE|TOTAL CLUSTERS|AVAIL CLUSTERS|SECTORS / CLUSTER|BYTES / SECTOR|\n");  
TCHAR   g_szTitle2[] = _T("|=====|==============|==============|=================|==============|\n");  
TCHAR   g_szLine[]   = _T("|  A: |              |              |                 |              |\n");  
  
void utoiRightJustified(TCHAR* szLeft, TCHAR* szRight, unsigned uVal);  
  
int main(int argc, char* argv[]) {  
   TCHAR szMsg[4200];  
   struct _diskfree_t df = {0};  
   ULONG uDriveMask = _getdrives();  
   unsigned uErr, uLen, uDrive;  
  
   printf(g_szBorder);  
   printf(g_szTitle1);  
   printf(g_szTitle2);  
  
   for (uDrive=1; uDrive<=26; ++uDrive) {  
      if (uDriveMask & 1) {  
         uErr = _getdiskfree(uDrive, &df);  
         memcpy(szMsg, g_szLine, sizeof(g_szLine));  
         szMsg[3] = uDrive + 'A' - 1;  
  
         if (uErr == 0) {  
            utoiRightJustified(szMsg+8,  szMsg+19, df.total_clusters);  
            utoiRightJustified(szMsg+23, szMsg+34, df.avail_clusters);  
            utoiRightJustified(szMsg+38, szMsg+52, df.sectors_per_cluster);  
            utoiRightJustified(szMsg+56, szMsg+67, df.bytes_per_sector);  
         }  
         else {  
            uLen = FormatMessage(FORMAT_MESSAGE_FROM_SYSTEM, NULL,  
                            uErr, 0, szMsg+8, 4100, NULL);  
            szMsg[uLen+6] = ' ';  
            szMsg[uLen+7] = ' ';  
            szMsg[uLen+8] = ' ';  
         }  
  
         printf(szMsg);  
      }  
  
      uDriveMask >>= 1;  
   }  
  
   printf(g_szBorder);  
}  
  
void utoiRightJustified(TCHAR* szLeft, TCHAR* szRight, unsigned uVal) {  
   TCHAR* szCur = szRight;  
   int nComma = 0;  
  
   if (uVal) {  
      while (uVal && (szCur >= szLeft)) {  
         if   (nComma == 3) {  
            *szCur = ',';  
            nComma = 0;  
         }  
         else {  
            *szCur = (uVal % 10) | 0x30;  
            uVal /= 10;  
            ++nComma;  
         }  
  
         --szCur;  
      }  
   }  
   else {  
      *szCur = '0';  
      --szCur;  
   }  
  
   if (uVal) {  
      szCur = szLeft;  
  
      while   (szCur <= szRight) {  
         *szCur = '*';  
         ++szCur;  
      }  
   }  
}  
```  
  
  **\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=**  
**&#124;LAUFWERK&#124;GESAMTCLUSTER&#124;VERFÜGBARE CLUSTER&#124;SEKTOREN \/ CLUSTER&#124;BYTES \/ SEKTOR&#124;**  
**&#124;\=\=\=\=\=&#124;\=\=\=\=\=\=\=\=\=\=\=\=\=\=&#124;\=\=\=\=\=\=\=\=\=\=\=\=\=\=&#124;\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=&#124;\=\=\=\=\=\=\=\=\=\=\=\=\=\=&#124;**  
**&#124;  A: &#124; Das Gerät ist nicht bereit.  &#124;                 &#124;              &#124;**  
**&#124;  C: &#124;    4.721.093 &#124;    3.778.303 &#124;               8 &#124;          512 &#124;**  
**&#124;  D: &#124;    1.956.097 &#124;    1.800.761 &#124;               8 &#124;          512 &#124;**  
**&#124;  E: &#124; Das Gerät ist nicht bereit.  &#124;                 &#124;              &#124;**  
**\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=**    
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Verzeichnissteuerung](../../c-runtime-library/directory-control.md)