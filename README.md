# Regenec_Genomica_español
Este es un repositorio en español donde estaré actualizando información acerca de herramientas de uso común para el análisis de datos genómicos

### Si encuentran un icono en la ventana izquierda llamado "regenec_cornejo" no hacer este paso

Esto se hace solo la primera vez! Luego de copiar la caja virtual en su máquina:

Antes de comenzar. Abran el programa de la caja virtual (VirtualBox Manager). En el menu, hagan click en "Archivo" y seleccionen la opción de "Importar aplicación..." y navegen hasta el Escritorio (donde probablemente este el archivo que copiamos) y seleccionen el archivo: "regenec_cornejo".

Una vez que la máquina esta instalada siempre se puede abrir el programa de la maquina virtual de la siguiente manera:
Esto creara un pequeño icono en la ventana izquierda del programa llamado regenec_cornejo. Si hacen doble click en ese icono, esto abrira la maquina virtual (espero).

## Analysis de Calidad de las Secuencias

En este breve tutorial solo veremos como usar las herramientas de analisis de calidad de secuencias.
Las instrucciones en cajas seran aquella que pueden copiar y pegar en el termina para poder hacer los analysis.

La herramienta que usaremos para analyzar la calidad de las secuencias es FastQC (https://www.bioinformatics.babraham.ac.uk/projects/fastqc/)

Una vez que hayamos iniciado la sesion en nuestra "maquina virtual", van a abrir un terminal y van a utlizar los siguientes comandos.

ejemplo general:
```bash
  cd regenec_project/data/
  fastqc --noextract --nogroup --outdir path_to_fastq_files_dir Mi_archivo.fastq.gz
```
Los archivos a utilizar son: 
  1.  Purple_Early_1_GTCCGC_S8_L001_R1_001.fastq.gz
  2.  Purple_Early_1_GTCCGC_S8_L001_R2_001.fastq.gz
  
ejemplo_específico:
```bash
  cd regenec_project/data/
  fastqc --noextract --nogroup --outdir ./ Purple_Early_1_GTCCGC_S8_L001_R1_001.fastq.gz
```
Vamos a analyzar juntos los resultados.

Una vez que hayamos decidido criterios para eliminar adaptadores y limpiar las secuencias, vamos a utilizar dos herramientas que funcionan de manera integrada para eliminar secuencias o fragmentos de secuencia que no se ajusten a nuestros criterios minimos de calidad.
TrimGalore (https://www.bioinformatics.babraham.ac.uk/projects/trim_galore/)
Cutadapt (https://cutadapt.readthedocs.io/en/stable/#)

```bash
/home/repository_software/trim_galore.0.4.3/trim_galore --output_dir my_trimed_data/ \
                  --quality 28 \
                  --illumina \
                  --phred33 \
                  --fastqc_args "--nogroup --noextract --outdir ./fastqc_postTrim" \
                  --stringency 6 \
                  --length 60 \
                  --clip_R1 10 \
                  --clip_R2 10 \
                  --paired \
                  Purple_Early_1_GTCCGC_S8_L001_R1_001.fastq.gz \
                  Purple_Early_1_GTCCGC_S8_L001_R2_002.fastq.gz
```

