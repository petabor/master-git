ts_wake_6 =
        test_wake %>%
        select(
                c(1:5)
        ) %>%
        filter(
                pairType_W_6 == "premise"
        ) %>%
        summarize(
                prop_W_6 = sum(key_resp_test.corr_W_6)/premTot, 
                rt_mean_W_6 = mean(key_resp_test.rt_W_6)
        )







class(ts_wake_6_select[, "pairType_W_6"])

colnames(ts_wake_6_select)[1]  ## accesing first element, but it's string

as_factor(colnames(ts_wake_6_select)[1])
rename(nep = as_factor(colnames(ts_wake_6_select)[1]))

?colnames

sum(ts_wake_6_select[,4])


ts_wake_6_select[,4]
ts_wake_6_select[,4]

?summarize




colnames(ts_wake_6_select) <- c("pairType", "letterPos1", "letterPos2", "key_resp_test.corr", "key_resp_test.rt")

ts_wake_6_select


ts_wake_6_multiple =
        ts_wake_6_select %>%
        group_by(
                pairType
        ) %>%
        summarize(
                tibble(
                        total_W = sum(key_resp_test.corr), 
                        rt_mean_W = mean(key_resp_test.rt)
                )
        ) %>%
        add_column(max_W = c(10, 20, 50, 10))

origColNames = colnames(ts_wake_6_select)[c(1, 4, 5)]
colnames(ts_wake_6_multiple) <- c(origColNames, "heh")





## part of a function


# dataSet_select =
#         dataSet %>%
#         filter(.data[df_colNames[[s]]:df_colNames[[e]]])



## function backup, 24.6.20
summary_subj_f <- function(dataSet, s, e){
        
        s = as.integer(s)
        e = as.integer(e)
        
        dataSet_select = dataSet[, c(s:e)]
        dataSet_select = as_tibble(dataSet_select)
        
        
        origColNames = colnames(dataSet_select)[c(1, 4, 5)]
        
        colnames(dataSet_select) <- c("pairType", "letterPos1", "letterPos2",
                                      "key_resp_test.corr", "key_resp_test.rt")
        
        dataSet_multiple =
                dataSet_select %>%
                group_by(
                        pairType
                ) %>%
                summarize(
                        tibble(
                                total_corr = sum(key_resp_test.corr), 
                                mean_rt = mean(key_resp_test.rt)
                        )
                ) %>%
                add_column(max = c(10, 20, 50, 10))
        
        colnames(dataSet_multiple) <- c(origColNames, "maximum")
        
        
        return(dataSet_multiple)
}





temp = as.tibble(cbind(nms = names(copy_subj_6), t(copy_subj_6)))
newTemp = as.tibble(temp[2:4,])


class(newTemp)


transpose_df <- function(df) {
        t_df <- data.table::transpose(df)
        colnames(t_df) <- rownames(df)
        rownames(t_df) <- colnames(df)
        t_df <- t_df %>%
                tibble::rownames_to_column(.data = .) %>%
                tibble::as_tibble(.)
        return(t_df)
}


transpose_df(copy_subj_6)



copy_subj_6 %>%
        gather(key = corr_cond_subj, value = value, 2:ncol(copy_subj_6)) %>% 
        spread_(key = names(copy_subj_6)[1],value = 'value')




copy_subj_6 = subj_6
copy_subj_11 = subj_11
copy_subj_15 = subj_15


copy_subj_6_head = slice_head(copy_subj_6)
copy_subj_6_tail = slice_tail(copy_subj_6)

copy_subj_6_tail_less =
        copy_subj_6_tail %>%
        select(-1) %>%
        rename(anchor_rt = anchor, oneDegree_rt = oneDegree, premise_rt = premise, twoDegree_rt = twoDegree)





bindCol = cbind(copy_subj_6_head, copy_subj_6_tail_less)





colN_wake = colnames(test_wake)
colN_wake[1]



oneSub_select <- 
        copy_test_sleep %>%
        dplyr::select(
                1:4 
        ) %>%
        filter(
                pairType_S_7 == "premise" | pairType_S_7 == "oneDegree" | pairType_S_7 == "twoDegree"
        )

oneSub_BC <- 
        oneSub_select %>%
        filter(
                letterPos1_S_7 == "B" & letterPos2_S_7 == "C" | 
                        letterPos1_S_7 == "C" & letterPos2_S_7 == "B"
        ) %>%
        summarise(
                tibble(
                        BC_S_7 = sum(key_resp_test.corr_S_7)
                )
        ) %>%
        gather(key = pair_cond_subj, value = value)
oneSub_CD <- 
        oneSub_select %>%
        filter(
                letterPos1_S_7 == "C" & letterPos2_S_7 == "D" | 
                        letterPos1_S_7 == "D" & letterPos2_S_7 == "C"
        ) %>%
        summarise(
                tibble(
                        CD_S_7 = sum(key_resp_test.corr_S_7)
                )
        ) %>%
        gather(key = pair_cond_subj, value = value)
oneSub_DE <- 
        oneSub_select %>%
        filter(
                letterPos1_S_7 == "D" & letterPos2_S_7 == "E" | 
                        letterPos1_S_7 == "E" & letterPos2_S_7 == "D"
        ) %>%
        summarise(
                tibble(
                        DE_S_7 = sum(key_resp_test.corr_S_7)
                )
        ) %>%
        gather(key = pair_cond_subj, value = value)
oneSub_BD <- 
        oneSub_select %>%
        filter(
                letterPos1_S_7 == "B" & letterPos2_S_7 == "D" | 
                        letterPos1_S_7 == "D" & letterPos2_S_7 == "B"
        ) %>%
        summarise(
                tibble(
                        DB_S_7 = sum(key_resp_test.corr_S_7)
                )
        ) %>%
        gather(key = pair_cond_subj, value = value)
oneSub_CE <- 
        oneSub_select %>%
        filter(
                letterPos1_S_7 == "C" & letterPos2_S_7 == "E" | 
                        letterPos1_S_7 == "E" & letterPos2_S_7 == "C"
        ) %>%
        summarise(
                tibble(
                        EC_S_7 = sum(key_resp_test.corr_S_7)
                )
        ) %>%
        gather(key = pair_cond_subj, value = value)
oneSub_BE <- 
        oneSub_select %>%
        filter(
                letterPos1_S_7 == "B" & letterPos2_S_7 == "E" | 
                        letterPos1_S_7 == "E" & letterPos2_S_7 == "B"
        ) %>%
        summarise(
                tibble(
                        BE_S_7 = sum(key_resp_test.corr_S_7)
                )
        ) %>%
        gather(key = pair_cond_subj, value = value)


pairType_df_ts = rbind(oneSub_CD, oneSub_CD, oneSub_DE, oneSub_BD, oneSub_CE, oneSub_BE)



str(subj)
str(cond)
str(pairType)

condition.sample = sample(c(0,1), size= sample.sim.size, replace=T)
str(condition.sample)


y = rnorm(n= sample.sim.size, sd=residual.variation, mean=0)
y = as.data.frame(y)
y = y[y$y >= 0 & y$y <=1, ]
y = y[1:40]
y = as.numeric(y)








rep(1:tb2[4], each = 10)


tb = tb[]/10

length(tr_tot_trim$participant)

bl_nr = 0
for(i in 1:length(tr_tot_trim$participant)){
        for(j in 1:length(tb)){
                bl_nr[i] = rep(1:tb[[j]][1], each = 10)
                
        }
}

rep(1:tb[[1]][1], each = 10)

rep(1:10, each = 18)

counter = 0
for(p in tr_tot_trim$participant){
        if(tr_tot_trim$participant == "6"){
                counter = counter + 1
        }       
}

print(counter)



tr_tot_trim_bla =
        tr_tot_trim %>%
        filter(
                participant == "6"
        )

for(p in tr_tot_trim[tr_tot_trim$participant == "6"]){
        if(tr_tot_trim$participant == "6"){
                print(length(tr_tot_trim$participant))
        }
        
}





temp = ""
for(i in 1:length(ts_tot_trim$participant)){
        if(ts_tot_trim$participant[i] == subj_wake){
                print(tokenFile_sel$Condition)
                temp[i] = "wake"
                #temp = append(temp, "wake")
        } else if(ts_tot_trim$participant[i] == subj_sleep$token_LS) {
                temp[i] = "sleep"
        }
}



class(subj_wake)
class(ts_tot_trim$participant)


table(tokenFile_sel_clean$Condition)


oneP_wake = rep("wake", nrBl*trial)
oneP_sleep = rep("sleep", nrBl*trial)

condCol = c(oneP_wake, oneP_sleep, oneP_sleep, oneP_wake, oneP_wake, oneP_wake,
            oneP_wake, oneP_wake, oneP_sleep, oneP_sleep, oneP_wake, oneP_wake)






## notes for analysis


***Rest notes***
        
        
        Check outliers

```{r outliers}

## maybe that need to be done in wide formate
# cutoff = qchisq(1 minus alpha <- 1-.05, df)



# df - number of columns <- how many variables IV <- ncol
# summary(IV < cutoff)
# delete outlier


## additivity

# correl = cor(data - IV, use= "pairwise.complete.obs")
# symnum(correl)





```


Based on the youtube video.

```{r assumptions}

## testing for additivity
## just to see how the matrix should look like, package: library(additivityTests)
set.seed(123)
subjects = rnorm(10)
treatments = rnorm(10)
noise = rnorm(100)/100
Y = matrix(rep(subjects, 10), 10, 10) + matrix(rep(treatments, each = 10), 10, 
                                               10) + noise ## look how the matrix should look like

## getting wide format from anova test and transform to matrix
wide_pilot = aov_pilot$data$wide
wide_pilot_short = wide_pilot[, c(-2, -1)]
wide_pilot_short = as.matrix(wide_pilot_short) ## to matrix

## conduct tukey test, additivity hypothesis should be rejected
tukey.test(wide_pilot_short)



# random = rchisq(nrow(dataset), 7) ## 7 just random number
# fake = lm(random ~ ., data = dataset) ## not subject number involved

# standardized = rstudnt(fake)
# fitted = scale(fake$fitted.values) ## should be randomly distributed around 0



## normality
# hist(standardized)


## linearity
# qqnorm(standardized)
# abline(0,1)


## homogeneity
# plot(fitted, standardized)
# abline=(0.0)
# abline(v=0)  ## should be centered around 0


## levenes test
## after running the model, without within variable, not sign good



# with(longdata, tapply(rating, lit(IV1), mean))
# with(longdata, tapply(rating, lit(IV2), mean))



## extracted from lm
lm_pilot = aov_pilot$lm
plot(lm_pilot$fitted.values ~ lm_pilot$residuals)
abline(0,0)
abline(v=0)




v = aov_pilot$Anova
aov_pilot$anova_table

# class(ts_first_selected$condition)

aov_pilot_noDV = ezANOVA(
        data = ts_first_selected,
        dv = prop,
        wid = participant,
        between = condition,
        within = pairType,
        type = 1
)
summary(aov_pilot_noDV)



aov_pilot

summary(aov_pilot)


leveneTest(ts_first_selected$prop ~ ts_first_selected$condition)

## running leven test for aov_pilot, centered around mean
test_levene(aov_pilot, center = mean)

## test of sphericity, Mauchly - not working now
test_sphericity(aov_pilot)

## running the model only with condition and specifying an error - not sure, check it later
btw1 = aov_car(
        prop ~ condition + Error(participant), data = ts_first_selected
)

## levene test only on between condition - which is condition
test_levene(btw1)



## normality of residuals

residuals(aov_pilot)
fitted.values(aov_pilot)

aov_pilot$lm$residuals
aov_pilot$lm$fitted.values


aov_pilot$data$wide

aov_pilot$Anova

cbind(fitted.values(aov_pilot), residuals(aov_pilot), ts_first_selected$prop)
cbind(residuals(aov_pilot), aov_pilot$lm$residuals)


## visual check
hist(residuals(aov_pilot), probability = T)
## add line
x = seq(from=min(residuals(aov_pilot)), to=max(residuals(aov_pilot)), length.out = 100)
lines(x=x, y=dnorm(x, mean = 0, sd=sd(residuals(aov_pilot))))


cbind(fitted.values(aov_pilot), residuals(aov_pilot))


# aov_pilot_simData <- aov_ez(
#         "subject",
#         "perf",
#         data = myData,
#         between = c("condition"),
#         within = c("pairType"),
#         type = 3
# )

# plot(fitted.values(aov_pilot_simData) ~ residuals(aov_pilot_simData))
# abline(v=0)



## sphericity only when more than 2 levels
# sum_aov_pilot_simData = summary(aov_pilot_simData)
# test_sphericity(aov_pilot_simData)


# hist(residuals(aov_pilot_simData))

min(residuals(aov_pilot))
max(residuals(aov_pilot))    ## -0.59 - 0.28


# min(residuals(aov_pilot_simData))   
# max(residuals(aov_pilot_simData))   ## -0.49 - 0.48


res = aov_pilot$lm$residuals
plot(res[,1], main="Premise residuals")
plot(res[,2], main="Inference residuals")


random = rchisq(nrow(ts_first_selected), 7)
fake = lm(random ~ ., data = ts_first_selected[,-3])
standardized = rstudent(fake)
fitted = scale(fake$fitted.values)

hist(standardized)
qqnorm(standardized)
abline(0,1)



plot(fitted.values(aov_pilot))
plot(residuals(aov_pilot))

plot(fitted.values(aov_pilot), residuals(aov_pilot))
abline(h=0)

aov_pilot$lm
qqnorm(residuals(aov_pilot))
qqline(residuals(aov_pilot))




## lsmeans
grid = lsmeans(aov_pilot, specs=c("condition", "pairType"))


grid_plot = as.data.frame(summary(grid))
pd <- position_dodge(0.1)
g4 <- ggplot(grid_plot, aes(x=factor(condition, level=c('wake', 'sleep')), y=lsmean,group=pairType,colour=pairType))+
        geom_errorbar(aes(ymin=lsmean-SE, ymax=lsmean+SE), width=.1,position=pd) +
        geom_line(position=pd)+
        geom_point(position=pd)+theme_classic()+
        labs(x="Condition", y="Mean")
print(g4)


## pairwise comparisons
compar = lsmeans(aov_pilot, specs = c("condition"))

## pairwise
contrast(compar, method = "pairwise")   ## adjusted for tukey method

## bonferroni
contrast(compar, method = "pairwise", adjust = "bonferroni")

## all pairwise comparison within each level of pairType
meansGrid2 = lsmeans(aov_pilot, ~condition|pairType)

compar_2 = contrast(meansGrid2, method="pairwise")
summary(compar_2)

## adjustment
summary(compar_2, by=NULL, adjus="holm")


sum_aov_pilot = summary(aov_pilot)
sum_aov_pilot$sphericity.tests

aov_pilot$Anova$type



```





## get rid of irrelevant columns
ts_first =
        ts_tot_trim %>%
        dplyr::select(
                key_resp_test.corr, pairType, participant, condition
        )

## change to factors
ts_first = 
        ts_first %>%
        mutate(
                pairType = as_factor(pairType),
                participant = as_factor(participant),
                condition = as_factor(condition)
        )

## calculate proportions
ts_first = 
        ts_first %>%
        group_by(
                pairType,
                condition,
                participant
                
        ) %>% 
        dplyr::summarise(
                tot = sum(key_resp_test.corr),
                n = n()
        ) %>%
        mutate(
                prop = tot/n
        ) %>%
        ungroup()

## drop not useful columns
ts_first =
        ts_first %>%
        dplyr::select(
                pairType, condition, participant, prop
        ) %>%
        filter(
                pairType == "premise" | pairType == "oneDegree" | pairType == "twoDegree"
        )

## colapse inference 

ts_first_collapse =
        ts_first %>%
        filter(
                pairType == "oneDegree" | pairType == "twoDegree"
        ) %>%
        group_by(
                participant,
                condition
        ) %>%
        dplyr::summarise(
                prop = mean(prop)
        )
ts_first_collapse =
        ts_first_collapse %>%
        add_column(
                pairType = rep("inference", times=length(ts_first_collapse$participant))
        )


## add the inference prop to premise
ts_first_all =
        ts_first %>%
        filter(
                pairType == "premise"
        )
ts_first_all = 
        full_join(
                ts_first_all, ts_first_collapse
        )







## get rid of irrelevant columns
ts_first =
        ts_tot_trim %>%
        dplyr::select(
                key_resp_test.corr, pairType, participant, condition
        )



## calculate proportions
ts_first = 
        ts_first %>%
        group_by(
                pairType,
                condition,
                participant
        ) %>% 
        dplyr::summarise(
                tot = sum(key_resp_test.corr),
                n = n()
        ) %>%
        mutate(
                prop = tot/n
        ) %>%
        ungroup()

## drop not useful columns
ts_first =
        ts_first %>%
        dplyr::select(
                pairType, condition, participant, prop
        ) %>%
        filter(
                pairType == "premise" | pairType == "oneDegree" | pairType == "twoDegree"
        )

## collapse inference 
ts_first_collapse =
        ts_first %>%
        filter(
                pairType == "oneDegree" | pairType == "twoDegree"
        ) %>%
        group_by(
                participant,
                condition
        ) %>%
        dplyr::summarise(
                prop = mean(prop)
        )
ts_first_collapse =
        ts_first_collapse %>%
        add_column(
                pairType = rep("inference", times=length(ts_first_collapse$participant))
        )

## add the inference prop to premise
ts_first_all =
        ts_first %>%
        filter(
                pairType == "premise"
        )
ts_first_all = 
        full_join(
                ts_first_all, ts_first_collapse
        )




## get rid of irrelevant columns
ts_first =
        ts_tot_trim %>%
        dplyr::select(
                key_resp_test.corr, pairType, participant, condition
        )

## change to factors
ts_first = 
        ts_first %>%
        mutate(
                pairType = as_factor(pairType),
                participant = as_factor(participant),
                condition = as_factor(condition)
        )

## calculate proportions
ts_first = 
        ts_first %>%
        group_by(
                pairType,
                condition,
                participant
                
        ) %>% 
        dplyr::summarise(
                tot = sum(key_resp_test.corr),
                n = n()
        ) %>%
        mutate(
                prop = tot/n
        ) %>%
        ungroup()

## drop not useful columns
ts_first =
        ts_first %>%
        dplyr::select(
                pairType, condition, participant, prop
        ) %>%
        filter(
                pairType == "premise" | pairType == "oneDegree" | pairType == "twoDegree"
        )

## colapse inference 

ts_first_collapse =
        ts_first %>%
        filter(
                pairType == "oneDegree" | pairType == "twoDegree"
        ) %>%
        group_by(
                participant,
                condition
        ) %>%
        dplyr::summarise(
                prop = mean(prop)
        )
ts_first_collapse =
        ts_first_collapse %>%
        add_column(
                pairType = rep("inference", times=length(ts_first_collapse$participant))
        )

## add the inference prop to premise
ts_first_all =
        ts_first %>%
        filter(
                pairType == "premise"
        )
ts_first_all = 
        full_join(
                ts_first_all, ts_first_collapse
        )

## sd total
sd_tot =
        ts_first_all %>%
        dplyr::summarise(
                sd_tot = sd(prop)
        ) %>%
        pull()

## creating the tresholds for each group - vary then
w_prem_th = 0.98
w_inf_th = 0.55
s_prem_th = 0.98
s_inf_th = 0.85

## double checking means
mean_w_prem = 0
mean_w_inf = 0
mean_s_prem = 0
mean_s_inf = 0


## loop paramaters
nr_sim = 200
p_value = 0
set.seed(123)

## parameters
nuSubj = 40
nrCond_bet = 2
nrCond_wth = 2
cond_bet = c("wake", "sleep")
cond_wth = c("premise", "inference")
myData = tibble()

for(j in 1:nr_sim){
        
        
        ## subject
        subject = rep(1:nuSubj, times = nrCond_bet)
        ## create IV within
        pair = rep(cond_wth, times = nuSubj)
        ## create IV between
        cond = rep(cond_bet, each = nrCond_bet, times = nuSubj/nrCond_bet)
        
        ## create empty tibble (to reset previous)
        myData = tibble(condition = cond, pairType = pair)
        
        ## arrange to pair type and condition so the dv is added appropriately
        myData =
                myData %>%
                arrange(
                        pairType,
                        condition
                )
        
        ## creating a sample of each treshold
        ## random sample with mean and sd from pilot data in range 0 and 1
        w_inf = rnorm(nuSubj/nrCond_bet, w_inf_th, sd_tot)
        for(a in 1:length(w_inf)){
                #print(w_inf[i])
                if(w_inf[a] >= 1){
                        w_inf[a] = 1
                } else if(w_inf[a] <= 0){
                        w_inf[a] = 0
                }
        }
        
        
        w_prem = rnorm(nuSubj/nrCond_bet, w_prem_th, sd_tot)
        for(b in 1:length(w_prem)){
                #print(w_inf[i])
                if(w_prem[b] >= 1){
                        w_prem[b] = 1
                } else if(w_inf[b] <= 0){
                        w_prem[b] = 0
                }
        }
        
        
        s_inf = rnorm(nuSubj/nrCond_bet, s_inf_th, sd_tot)
        for(c in 1:length(s_inf)){
                #print(w_inf[i])
                if(s_inf[c] >= 1){
                        s_inf[c] = 1
                } else if(w_inf[c] <= 0){
                        s_inf[c] = 0
                }
        }
        
        
        s_prem = rnorm(nuSubj/nrCond_bet, s_prem_th, sd_tot)
        for(d in 1:length(s_prem)){
                #print(w_inf[i])
                if(s_prem[d] >= 1){
                        s_prem[d] = 1
                } else if(s_prem[d] <= 0){
                        s_prem[d] = 0
                }
        }
        
        
        ## performance bind - the order is dependent on the arrangment before
        perf = c(s_inf, w_inf, s_prem, w_prem)
        
        ## add performance
        myData <- 
                myData %>%
                add_column(
                        perf = perf, .after = "pairType"
                ) 
        
        # convert to factor
        myData <- 
                myData %>%
                add_column(
                        subject = subject, .before = "condition"
                ) %>%
                mutate(
                        subject = as.factor(subject),
                        pairType = as.factor(pairType),
                        condition = as.factor(condition)
                )
}



## get rid of irrelevant columns
other =
        ts_tot_trim %>%
        dplyr::select(
                key_resp_test.corr, pairType, participant, condition, 
                trBlocks, letterPos1, letterPos2
        ) 

## calculate proportions
other = 
        other %>%
        group_by(
                pairType,
                condition,
                participant,
                trBlocks, 
                letterPos1, 
                letterPos2
                
        ) %>% 
        dplyr::summarise(
                tot = sum(key_resp_test.corr),
                n = n()
        ) %>%
        mutate(
                prop = tot/n
        ) %>%
        ungroup()

## drop not useful columns
other =
        other %>%
        dplyr::select(
                pairType, condition, participant, prop, 
                trBlocks, letterPos1, letterPos2
        ) %>%
        filter(
                pairType == "premise" | pairType == "oneDegree" | pairType ==
                        "twoDegree"
        ) %>%
        unite(    ## add pos1 and pos2 together, easier
                "lettPos", letterPos1:letterPos2, remove = TRUE  
        )



other_collapse_deg =
        other %>%
        filter(
                pairType == "oneDegree" | pairType == "twoDegree"
        ) %>%
        group_by(
                participant,
                condition,
                lettPos,
                trBlocks
        ) %>%
        dplyr::summarise(
                prop = mean(prop)
        ) 

other_collapse_deg =
        other_collapse_deg %>%
        add_column(
                pairType = rep("inference",
                               times=length(other_collapse_deg$participant))
        ) 


other_collapse_middPrem =
        other %>%
        filter(
                pairType == "premise"
        ) 


other_collapse_middPrem =  ## filter just middle pairs
        other_collapse_middPrem %>%
        filter(
                lettPos != "A_B" & lettPos != "B_A" & lettPos != "E_F" & lettPos != "F_E"
        ) %>%
        group_by(
                participant,
                condition, 
                trBlocks, 
                lettPos
        ) %>%
        dplyr::summarise(
                prop = mean(prop)
        ) 

other_collapse_middPrem =
        other_collapse_middPrem %>%
        add_column(
                pairType = rep("midd_prem",
                               times=length(other_collapse_middPrem$participant))
        )

other_merge = 
        full_join(
                other_collapse_deg, other_collapse_middPrem
        ) %>%
        mutate(
                pairType = as_factor(pairType),  ## change to factors
                participant = as_factor(participant),
                condition = as_factor(condition)
        )



