---
title: "senti_collocaation"
author: "Po Ya Angela Wang"
date: "Friday, December 12, 2014"
output: html_document
---
###Introduction:
   To retrieve the top three frequent verbs collocated before and after the sentiment words from the Sinica corpus.

##1st Verb after the sentiment words
```{r}
senti_position<-list()
af<-list()
afverb<-list()
for (i in 1:256){
        senti_position[[i]]<-grep(paste("^",wordlists[i],"\\(",sep=""),sinica_words,value=F,fixed=F)
        af[[i]]<-senti_position[[i]]+1
        collocatesaft<-sinica_words[af[[i]]]
        collocatesafttb<- table(collocatesaft)
        collocatesaftdf<- data.frame(collocatesafttb)
        sort_collocatesaftdf<- sort(collocatesaftdf[,1],decreasing= T)
        afverb[[i]]<-head(grep("V",sort_collocatesaftdf,value=T),n=3)       
}
str(afverb)
save(afverb, file="/home/amber/senti/afverb")
load(file="/home/amber/senti/afverb")
```
##2nd Verb after the sentiment words
```{r}
senti_position<-list()
af<-list()
afverb2<-list()
for (i in 1:256){
        senti_position[[i]]<-grep(paste("^",wordlists[i],"\\(",sep=""),sinica_words,value=F,fixed=F)
        af[[i]]<-senti_position[[i]]+2
        collocatesaft<-sinica_words[af[[i]]]
        collocatesafttb<- table(collocatesaft)
        collocatesaftdf<- data.frame(collocatesafttb)
        sort_collocatesaftdf<- sort(collocatesaftdf[,1],decreasing= T)
        afverb2[[i]]<-head(grep("V",sort_collocatesaftdf,value=T),n=3)       
}
str(afverb2)
save(afverb2, file="/home/amber/senti/afverb2")
load(file="/home/amber/senti/afverb2")
```
##3rd Verb after the sentiment words
```{r}
senti_position<-list()
af<-list()
afverb3<-list()
for (i in 1:256){
        senti_position[[i]]<-grep(paste("^",wordlists[i],"\\(",sep=""),sinica_words,value=F,fixed=F)
        af[[i]]<-senti_position[[i]]+3
        collocatesaft<-sinica_words[af[[i]]]
        collocatesafttb<- table(collocatesaft)
        collocatesaftdf<- data.frame(collocatesafttb)
        sort_collocatesaftdf<- sort(collocatesaftdf[,1],decreasing= T)
        afverb3[[i]]<-head(grep("V",sort_collocatesaftdf,value=T),n=3)       
}
str(afverb3)
save(afverb3, file="/home/amber/senti/afverb3")
load(file="/home/amber/senti/afverb3")
```

##1st Verb before the sentiment words
```{r}
senti_position<-list()
af<-list()
bfverb1<-list()
for (i in 1:256){
        senti_position[[i]]<-grep(paste("^",wordlists[i],"\\(",sep=""),sinica_words,value=F,fixed=F)
        af[[i]]<-senti_position[[i]]-1
        collocatesaft<-sinica_words[af[[i]]]
        collocatesafttb<- table(collocatesaft)
        collocatesaftdf<- data.frame(collocatesafttb)
        sort_collocatesaftdf<- sort(collocatesaftdf[,1],decreasing= T)
        bfverb1[[i]]<-head(grep("V",sort_collocatesaftdf,value=T),n=3)       
}
str(bfverb1)
save(bfverb1, file="/home/amber/senti/bfverb1")
load(file="/home/amber/senti/bfverb1")
```
##2nd Verb before the sentiment words
```{r}
senti_position<-list()
af<-list()
bfverb2<-list()
for (i in 1:256){
        senti_position[[i]]<-grep(paste("^",wordlists[i],"\\(",sep=""),sinica_words,value=F,fixed=F)
        af[[i]]<-senti_position[[i]]-2
        collocatesaft<-sinica_words[af[[i]]]
        collocatesafttb<- table(collocatesaft)
        collocatesaftdf<- data.frame(collocatesafttb)
        sort_collocatesaftdf<- sort(collocatesaftdf[,1],decreasing= T)
        bfverb2[[i]]<-head(grep("V",sort_collocatesaftdf,value=T),n=3)       
}
str(bfverb2)
save(bfverb2, file="/home/amber/senti/bfverb2")
load(file="/home/amber/senti/bfverb2")
```
##3rd Verb after the sentiment words
```{r}
senti_position<-list()
af<-list()
bfverb3<-list()
for (i in 1:256){
        senti_position[[i]]<-grep(paste("^",wordlists[i],"\\(",sep=""),sinica_words,value=F,fixed=F)
        af[[i]]<-senti_position[[i]]-3
        collocatesaft<-sinica_words[af[[i]]]
        collocatesafttb<- table(collocatesaft)
        collocatesaftdf<- data.frame(collocatesafttb)
        sort_collocatesaftdf<- sort(collocatesaftdf[,1],decreasing= T)
        bfverb3[[i]]<-head(grep("V",sort_collocatesaftdf,value=T),n=3)       
}
str(bfverb3)
save(bfverb3, file="/home/amber/senti/bfverb3")
load(file="/home/amber/senti/bfverb3")
```


