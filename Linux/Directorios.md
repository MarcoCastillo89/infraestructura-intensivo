# Directorios del sistema Linux - Explicación completa

## 1. `/` – El directorio raíz
Punto de inicio del sistema de archivos. Contiene todo el sistema, incluyendo todos los demás directorios y archivos.  
- **General**: Sí, siempre existe.

## 2. `/bin` – Binarios de usuario esenciales
Comandos básicos como `ls`, `cp`, `mv`, `bash`. Necesarios para el modo de recuperación y el arranque.  
- **General**: Sí (aunque en algunas distribuciones recientes `/bin` es un enlace simbólico a `/usr/bin`).

## 3. `/boot` – Archivos de arranque estáticos
Contiene el kernel (`vmlinuz`), la imagen initrd, y el gestor de arranque (GRUB).  
- **General**: Sí.

## 4. `/cdrom` – Punto de montaje histórico para CD-ROM
Antiguamente usado para montar CDs automáticamente. Hoy es raro; la mayoría usa `/media` o monta en `/run/media/usuario`.  
- **Específico**: Solo en algunas distribuciones antiguas o configuraciones heredadas. En sistemas modernos no suele existir.

## 5. `/dev` – Archivos de dispositivo
Contiene archivos especiales que representan hardware (discos, terminales, etc.). Gestionado por el sistema (udev).  
- **General**: Sí (sistema de archivos virtual en memoria).

## 6. `/etc` – Archivos de configuración
Configuraciones del sistema y de aplicaciones (ej. `/etc/passwd`, `/etc/network/interfaces`).  
- **General**: Sí.

## 7. `/home` – Carpetas de inicio de los usuarios normales
Cada usuario no root tiene su subdirectorio aquí. Almacena documentos, configuraciones personales, etc.  
- **General**: Sí (aunque puede estar vacío si no hay usuarios).

## 8. `/lib` – Bibliotecas compartidas esenciales
Librerías dinámicas (`.so`) necesarias para los binarios de `/bin` y `/sbin`. También módulos del kernel.  
- **General**: Sí (a veces es un enlace a `/usr/lib`).

## 9. `/lost+found` – Archivos recuperados
Creado por sistemas de archivos tipo ext3/ext4 para guardar fragmentos de archivos dañados recuperados por `fsck`.  
- **Específico**: Solo en sistemas de archivos ext3/ext4 (los más comunes, pero si usas Btrfs, XFS, ZFS, no aparece).

## 10. `/media` – Medios extraíbles
Punto de montaje automático para USB, CD, tarjetas SD.  
- **General**: Sí (en distribuciones modernas).

## 11. `/mnt` – Puntos de montaje temporales
Directorio vacío para que el administrador monte manualmente sistemas de archivos temporales.  
- **General**: Sí.

## 12. `/opt` – Paquetes opcionales
Para software adicional o comercial que no sigue la estructura estándar (ej. `/opt/google/chrome`).  
- **General**: Sí (aunque suele estar vacío por defecto).

## 13. `/proc` – Kernel y archivos de proceso
Sistema de archivos virtual que proporciona información de procesos y del kernel en tiempo real (ej. `/proc/cpuinfo`).  
- **General**: Sí.

## 14. `/root` – Directorio de inicio del superusuario (`root`)
Carpeta personal de root. No debe confundirse con `/`.  
- **General**: Sí.

## 15. `/run` – Archivos de estado de la aplicación
Sistema de archivos en RAM que guarda datos volátiles desde el arranque (PIDs, sockets, etc.). Reemplaza a `/var/run`.  
- **General**: Sí (en distribuciones modernas con systemd o similares).

## 16. `/sbin` – Binarios de administración del sistema
Ejecutables para tareas de mantenimiento (`fdisk`, `reboot`, `iptables`). Normalmente solo ejecutables por root.  
- **General**: Sí (a veces enlazado a `/usr/sbin`).

## 17. `/selinux` – Sistema de archivos virtual SELinux
Punto de montaje para las políticas y contexto de SELinux.  
- **Específico**: Solo en distribuciones con SELinux activado por defecto (Fedora, RHEL, CentOS). En Debian/Ubuntu/Arch no suele existir.

## 18. `/srv` – Datos de servicio
Almacena datos de servicios del sistema (ej. `/srv/www` para servidores web).  
- **General**: Sí (aunque a menudo está vacío, pero el directorio existe).

## 19. `/tmp` – Archivos temporales
Directorio para archivos efímeros. Cualquier usuario puede escribir; se limpia al reiniciar.  
- **General**: Sí.

## 20. `/usr` – Binarios de usuario y datos de solo lectura
Directorio grande con programas, bibliotecas, documentación. Subdirectorios: `/usr/bin`, `/usr/lib`, `/usr/local`, etc.  
- **General**: Sí.

## 21. `/var` – Archivos de datos variables
Almacena logs (`/var/log`), correo (`/var/mail`), colas de impresión, archivos temporales persistentes, etc.  
- **General**: Sí.

---

## Resumen de directorios específicos (no universales):
- `/cdrom` – solo en sistemas antiguos o configuraciones heredadas.
- `/lost+found` – solo con sistema de archivos ext3/ext4.
- `/selinux` – solo en distribuciones con SELinux (Fedora, RHEL, CentOS).

Todos los demás son universales en cualquier instalación típica de Linux.
