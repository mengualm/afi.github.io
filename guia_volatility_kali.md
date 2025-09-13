
# Guía de Instalación de Volatility 2 en Kali Linux

Volatility es una herramienta de análisis forense de memoria muy utilizada en investigaciones de seguridad. Esta guía te ayudará a instalar **Volatility 2** en **Kali Linux**, paso a paso.

---

## 🧠 Paso 1: Preparar el sistema
Actualiza los paquetes e instala las dependencias necesarias:

```bash
sudo apt update
sudo apt install -y build-essential git libdistorm3-dev yara libraw1394-11 libcapstone-dev capstone-tool tzdata
```

---

## 🐍 Paso 2: Instalar Python 2 y pip2
Volatility 2 depende de Python 2. Instálalo junto con su gestor de paquetes:

```bash
sudo apt install -y python2 python2.7-dev libpython2-dev curl
curl https://bootstrap.pypa.io/pip/2.7/get-pip.py -o get-pip.py
sudo python2 get-pip.py
sudo python2 -m pip install -U setuptools wheel
```

---

## 📦 Paso 3: Instalar dependencias de Volatility
Instala los paquetes necesarios para que Volatility funcione correctamente:

```bash
python2 -m pip install -U distorm3 pycrypto pillow openpyxl ujson pytz ipython capstone
```

---

## 🧩 Paso 4: Instalar el plugin Yara (versión específica)

```bash
pip2 install yara-python==3.8.0
git clone https://github.com/VirusTotal/yara-python
cd yara-python
git checkout v3.8.0
```

---

## 📥 Paso 5: Clonar e instalar Volatility 2

```bash
git clone https://github.com/volatilityfoundation/volatility.git
cd volatility
python2 vol.py --info
```

---

## 🛠️ Paso 6: Hacer Volatility accesible desde cualquier parte
Agrega Volatility al PATH para ejecutarlo fácilmente:

```bash
echo 'export PATH=$HOME/.local/bin:$PATH' >> ~/.bashrc
source ~/.bashrc
```

---

## ✅ Verificación final
Ejecuta el siguiente comando para verificar que Volatility está instalado correctamente:

```bash
python2 vol.py --info
```

Si ves una lista de plugins, ¡la instalación fue exitosa!

---

## 📚 Recursos adicionales
- [Repositorio oficial de Volatility](https://github.com/volatilityfoundation/volatility)
- [Documentación de Yara](https://yara.readthedocs.io/)

