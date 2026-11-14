# Olah Data Semarang
# WhatsApp : +6285227746673
# IG : @olahdatasemarang_
# Causal Mediation Analysis in Presence of Multiple Mediators Uncausally Related Use multimediate With (In) R Software
install.packages("multimediate")
library("multimediate")
# Estimate Causal Mediation Analysis in Presence of Multiple Mediators Uncausally Related Use multimediate With (In) R Software
multimediate = read.csv("https://raw.githubusercontent.com/timbulwidodostp/multimediate/main/multimediate/multimediate.csv",sep = ";")
M1reg <- lm(M1 ~ Treatment + C1 + C2, data = multimediate)
M2reg <- lm(M2 ~ Treatment + C1 + C3, data = multimediate)
M3reg <- lm(M3 ~ Treatment + C1, data = multimediate)
Yreg <- lm(Outcome ~ Treatment + M1 + M2 + M3 + C1 + C2 + C3, data = multimediate)
multimediate <- multimediate(lmodel.m = list(M1reg, M2reg, M3reg), correlated = TRUE, model.y = Yreg, 
treat = "Treatment", treat.value = 1, control.value = 0, J = 100, conf.level = 0.95, verbose = FALSE)
summary(multimediate)
# Causal Mediation Analysis in Presence of Multiple Mediators Uncausally Related Use multimediate With (In) R Software
# Olah Data Semarang
# WhatsApp : +6285227746673
# IG : @olahdatasemarang_
# Finished