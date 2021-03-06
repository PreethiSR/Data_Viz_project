Data Product- America’s unique gun violence problem
================
Preethi S Ranganathan
06/02/2018

**Data Product:** America’s unique gun violence problem
<https://www.vox.com/policy-and-politics/2017/10/2/16399418/us-gun-violence-statistics-maps-charts>

The data product, is about the Gun Violence in the United States. The
maps and charts in the data product show what gun violence looks like
compared with the rest of the world and also how prevalent it is in the
US, why it happens, and why it’s such a tough problem to fix.

There are two objectives with this project:

1.  Redesign product - Replication and Redesign of the original data
    product.
2.  Deceptive product - Development of deceptive data product, which
    explains intentional and unintentional distortions to the data.

There are three claims in each product, which are discussed in detail
below:

## Redesign product:

### Claim 1: United States has the highest firearm homicide and suicide rates among the top most developed countries.

#### Chart from Vox:

``` r
img <- readPNG( '/Users/preethiranganathan/Documents/Santa Clara/data viz/indiv proj/Image4.png',native=TRUE)
plot.new() 
rasterImage(img,0,0,1,1)
```

![](Final_indiv_project_files/figure-gfm/Original%20Claim%201-1.png)<!-- -->

<sup>Source: Vox
<https://www.vox.com/policy-and-politics/2017/10/2/16399418/us-gun-violence-statistics-maps-charts>
</sup>

This chart tells us about the mass shootings, which make up a tiny
portion of America’s firearm deaths, since 2012.

#### First Redesign version:

The first redesign version is a replication of the original chart in the
data product with the only change being the number of casualties
represented by both color and size of circles. This change was made to
show the severity of shootings more
clearly.

``` r
img <- readPNG( '/Users/preethiranganathan/Documents/Santa Clara/data viz/indiv proj/Image3.png',native=TRUE)
plot.new() 
rasterImage(img,0,0,1,1)
```

![](Final_indiv_project_files/figure-gfm/Redesign%20First%20Claim%201-1.png)<!-- -->

<sup>Source: Gun Violence Archive: <http://www.gunviolencearchive.org>
</sup>

#### Final Redesign version:

The main intent of this graph is to show the severity and importance of
gun violence in the US. The first claim ‘There has been a lot of mass
shootings since 2012’ do not reflect that point, precisely. Hence, in
the revised version, I altered the claim to indicate the importance of
gun violence.

The altered claim is ‘United States has the highest firearm homicide and
suicide rates among the top most developed countries’. This claim would
convey the message of why firearm violence needs to be addressed
immediately.

The other point is that the original chart is a geographical map. But it
is not a good idea to have this kind of map as a warrant for expressing
number of casualties. It shows that gun casualties occur at places with
high population.

For coming up with this chart, I made a comparison of homicide and
suicides rates of US with other developed countries to show that United
States has the highest firearm homicide and suicide rates among the top
most developed countries.

The developed countries list is from
<https://www.topteny.com/top-10-highly-developed-countries-in-the-world/>

``` r
ghom= read.csv('/Users/preethiranganathan/Documents/Santa Clara/data viz/indiv proj/homicide_rate_global.csv',header=TRUE)

ghom1=ghom[ghom$Location %in% c('Canada','Germany' ,'United States','Netherlands','Australia','United Kingdom','Norway','New Zealand', 'Switzerland'),] 

p1<-ggplot(ghom1, aes(reorder(ghom1$Location, ghom1$Value),Value)) +geom_col(position ='dodge') + labs(y = "Firearm Homicides per 100,000 people",x='')+ coord_flip()+theme_minimal()+ggtitle('US has the highest firearm homicide and suicide rates among the top most developed countries')+theme(panel.grid.major = element_blank(), panel.grid.minor = element_blank(),axis.line = element_line(colour = "black"), plot.title = element_text( size=9),axis.title= element_text( size=8))

gsuicide= read.csv('/Users/preethiranganathan/Documents/Santa Clara/data viz/indiv proj/suicide_rate_global.csv',header=TRUE)
gsuicide1=gsuicide[gsuicide$Location %in% c('Canada','Germany' ,'United States', 'Netherlands','Australia','United Kingdom','Norway','New Zealand','Switzerland'),] 

p2<-ggplot(gsuicide1, aes(reorder(gsuicide1$Location, gsuicide1$Value),Value)) +geom_col(position ='dodge') + labs(y = "Firearm Suicides per 100,000 people",x='')+ coord_flip()+theme_minimal()+theme(panel.grid.major = element_blank(), panel.grid.minor = element_blank(),axis.line = element_line(colour = "black"), plot.title = element_text( size=11),axis.title= element_text( size=8))

grid.arrange(p1,p2,nrow=2)
```

![](Final_indiv_project_files/figure-gfm/Redesign%20Final%20Claim%201-1.png)<!-- -->

<sup>Source: Institute for Health Metrics and Evaluation:
<https://vizhub.healthdata.org/gbd-compare/></sup>

This dataset has firearm-related homicide rates for all countries for
the year 2016 and I have picked only few developed countries for
comparison as it is only fair to compare death rates of countries with
similiar living standards, given by Human Development Index.

Use of colors is not necessary here because the bars itself gives a good
comparison of death rates for different
countries.

### Claim 2: Firearm suicide rates has been increasing in the US over years.

#### Chart from Vox:

``` r
img <- readPNG( '/Users/preethiranganathan/Documents/Santa Clara/data viz/indiv proj/Image 1.png',native=TRUE)
plot.new() 
rasterImage(img,0,0,1,1)
```

![](Final_indiv_project_files/figure-gfm/Original%20Claim%202-1.png)<!-- -->

<sup>Source: Vox
<https://www.vox.com/policy-and-politics/2017/10/2/16399418/us-gun-violence-statistics-maps-charts></sup>

Chart 10 in Vox claims that most firearm deaths are suicides. In this
chart, we see a time series of firearm suicides and homicides from 1999
to 2016 and we can see that number of firearm homicides is always less
than the number of firearm suicides over years.

#### First Redesign version:

I made two charts for the first version, first one similiar to the vox
chart except that the number of deaths is now normalized per 100,000
people. It still shows the same homicide and suicide trend.

The second chart, shows the suicides as a perecentage of firearm deaths.
I thought it is a good idea, because the claim talks about suicides as a
proportion of firearm deaths, which is what the claim ‘Most gun deaths
are suicides’ tries to
convey.

``` r
img <- readPNG( '/Users/preethiranganathan/Documents/Santa Clara/data viz/indiv proj/Image5.png',native=TRUE)
plot.new() 
rasterImage(img,0,0,1,1)
```

![](Final_indiv_project_files/figure-gfm/Redesign%20First%20Claim%202-1.png)<!-- -->

<sup> Source: Centers for Disease Control and Prevention:
<https://webappa.cdc.gov/sasweb/ncipc/mortrate10_us.html> </sup>

Note that the data pixel ratio is very low in the above chart, as only
the top of the bars convey information. This will be improved in the
final
version.

``` r
img <- readPNG( '/Users/preethiranganathan/Documents/Santa Clara/data viz/indiv proj/Image7.png',native=TRUE)
plot.new() 
rasterImage(img,0,0,1,1)
```

![](Final_indiv_project_files/figure-gfm/Redesign%20First%20Claim%202%20cont..-1.png)<!-- -->

<sup> Source: Centers for Disease Control and Prevention:
<https://webappa.cdc.gov/sasweb/ncipc/mortrate10_us.html> </sup>

#### Final Redesign version:

The point that I wanted to make with the claim is that firearm suicides,
being the major proportion of firearm deaths are increasing over the
years.

First, I designed a chart to convey the message of how firearm suicide
rates are increasing in the US over years and then the second chart to
explain why we have to address suicides immediately.

The dataset used here has raw number of suicides every year from 1999 to
2016. It makes more sense to use normalized suicide rates as metric,
because using raw numbers would not exclude the population factor into
account, as it keeps increasing over years.

``` r
#Firearm Suicide data files from 1999 to 2015
suicidefiles <- list.files(path='~/Documents/Santa Clara/data viz/indiv proj/firearm_suicide',full.names = TRUE, pattern = ".csv")
d=data.frame()
for(i in 1:length(suicidefiles)){
  d=rbind(read.table(suicidefiles[i],sep=',',header=TRUE),d)
}
suicide=data.frame(d[,6],d[,8],d[,9],d[,10])
suicide=unique(suicide)
colnames(suicide)<- c('Year','Suicide_Method','Deaths','Population')
#Firearm Suicides per 100K
suicide['Num_of_Deaths_in_100K']=(suicide['Deaths']/suicide['Population'])*100000
suicide=suicide[sort(suicide$Year,decreasing=FALSE,index.return=TRUE)$ix,]

ggplot(suicide) +geom_line(aes(Year, Num_of_Deaths_in_100K ))+ggtitle('Firearm suicide rates has been increasing in the US over years')+theme(panel.grid.major = element_blank(), panel.grid.minor = element_blank(), panel.background = element_blank(),  axis.line = element_line(colour = "black"), plot.title = element_text( size=11), axis.title= element_text( size=9))+ labs(x='Year',y = "Number of suicides per 100,000 people") + scale_x_continuous(breaks=seq(1999,2016,1))
```

![](Final_indiv_project_files/figure-gfm/Redesign%20Final%20Claim%202-1.png)<!-- -->

<sup> Source: Centers for Disease Control and Prevention
(<https://webappa.cdc.gov/sasweb/ncipc/mortrate10_us.html>) </sup>

The number of firearm suicides was gradually dropping from 2002 to 2006,
but it started increasing rapidly since 2007. This could be because of
global financial crisis with high numbers of people killing themselves
suffering heavy job losses.
<https://journalistsresource.org/studies/society/public-health/suicides-during-great-recession-united-states-canada-europe>

Added to this, people pre-dominantly choose firearm for killing
themselves compared to any other methods in the US.

``` r
#Poisoning Suicide data files from 1999 to 2015
psuicidefiles <- list.files(path='~/Documents/Santa Clara/data viz/indiv proj/poisoning_suicide',full.names = TRUE, pattern = ".csv")
d=data.frame()
for(i in 1:length(psuicidefiles)){
  d=rbind(read.table(psuicidefiles[i],sep=',',header=TRUE),d)
}
psuicide=data.frame(d[,6],d[,8],d[,9],d[,10])
psuicide=unique(psuicide)
colnames(psuicide)<- c('Year','Suicide_Method','Deaths','Population')
psuicide['Suicide_Method']='Poisioning'

#Poisoning Suicides per 100K
psuicide['Num_of_Deaths_in_100K']=(psuicide['Deaths']/psuicide['Population'])*100000

#Cut Suicide data files from 1999 to 2015
csuicidefiles <- list.files(path='~/Documents/Santa Clara/data viz/indiv proj/cut_suicide',full.names = TRUE, pattern = ".csv")
d=data.frame()
for(i in 1:length(psuicidefiles)){
  d=rbind(read.table(csuicidefiles[i],sep=',',header=TRUE),d)
}
csuicide=data.frame(d[,6],d[,8],d[,9],d[,10])
csuicide=unique(csuicide)
colnames(csuicide)<- c('Year','Suicide_Method','Deaths','Population')
csuicide['Suicide_Method']='Cut/Pierce'

#Cut Suicides per 100K
csuicide['Num_of_Deaths_in_100K']=(csuicide['Deaths']/csuicide['Population'])*100000

#Suffocation Suicide data files from 1999 to 2015
ssuicidefiles <- list.files(path='~/Documents/Santa Clara/data viz/indiv proj/suffocation_suicide',full.names = TRUE, pattern = ".csv")
d=data.frame()
for(i in 1:length(ssuicidefiles)){
  d=rbind(read.table(ssuicidefiles[i],sep=',',header=TRUE),d)
}
ssuicide=data.frame(d[,6],d[,8],d[,9],d[,10])
ssuicide=unique(ssuicide)
colnames(ssuicide)<- c('Year','Suicide_Method','Deaths','Population')
#Suffocation Suicides per 100K
ssuicide['Num_of_Deaths_in_100K']=(ssuicide['Deaths']/ssuicide['Population'])*100000
ssuicide['Suicide_Method']='Suffocation'
suicide['Suicide_Method']='Firearm'

#Combining rows of homicide and suicide data frame.
totalsuicides=rbind(suicide,csuicide,psuicide,ssuicide)
compressed <- totalsuicides %>% group_by(Suicide_Method) %>% summarize(total=sum(Deaths,na.rm=TRUE))

slices= compressed$total
lbls =compressed$Suicide_Method
pie(slices, labels = lbls, main="Firearm suicides form the major proportion of suicides in the US",col=c('#B79F00','#00BFC4','orange','#F8766D'),font.main=1,cex.main =0.9)
```

![](Final_indiv_project_files/figure-gfm/Redesign%20Final%20Claim%202%20cont..-1.png)<!-- -->

<sup> Source: Centers for Disease Control and Prevention:
<https://webappa.cdc.gov/sasweb/ncipc/mortrate10_us.html> </sup>

Contrasting colors are used here to just show difference between
propotion of suicide methods and it doesn’t convey any meaning, in
particular.

Note: Throughout the final version charts, the above colors will be used
uniformly (only if colors are
needed).

### Claim 3: States with the most guns report the most firearm homicides and suicides.

#### Chart from Vox:

``` r
img <- readPNG( '/Users/preethiranganathan/Documents/Santa Clara/data viz/indiv proj/Image 2.png',native=TRUE)
plot.new() 
rasterImage(img,0,0,1,1)
```

![](Final_indiv_project_files/figure-gfm/Original%20Claim%203-1.png)<!-- -->

<sup>Source: Vox
<https://www.vox.com/policy-and-politics/2017/10/2/16399418/us-gun-violence-statistics-maps-charts></sup>

The claim in the original chart states that more guns, more sucides.
Different colors are used to compare between firearm and non-firearm
suicides. The left-most bars indicate states with high gun ownership and
the right-most bars indicate states with low gun ownership.

#### First Redesign Version:

While redesigning the chart, I made a change to present two side-by-side
charts, as it takes time to understand what highest and lowest rates
mean.

Here, we have grouped top 10 states with high gun ownership rate into
one group and top 10 states with low gun ownership rate into anothe
group. This makes the warrant more clear to support the claim ‘more guns
more suicides’.

Red color is used here as I connected red to violence. This assumption
is far-fetched. Not all audience will make the same connection. Hence,
it is better to go with black and white, as colors doesn’t convey
anything here. This will be improved in the final version
chart.

``` r
img <- readPNG( '/Users/preethiranganathan/Documents/Santa Clara/data viz/indiv proj/Image 6.png',native=TRUE)
plot.new() 
rasterImage(img,0,0,1,1)
```

![](Final_indiv_project_files/figure-gfm/Redesign%20First%20Claim%203-1.png)<!-- -->

<sup>Sources: N.C. State Center for Health Statistics-
<http://www.washingtonpost.com/wp-srv/health/interactives/guns/ownership.html?noredirect=on>,<br />
Gun control laws - <https://www.statefirearmlaws.org/table.html></sup>

#### Final Redesign Version:

In the first version, only firearm suicides were compared in states with
different levels of gun ownership rates. Hence, including homcides rates
for different gun ownership levels in the final version. And, there is
no point of showing non-firearm suicide rates, as the intent is to
compare firearm rates between states with high and low gun ownership
rates.

``` r
#gun ownership survey data
df = read.xls ("/Users/preethiranganathan/Documents/Santa Clara/data viz/indiv proj/gun ownership statewise.xlsx", sheet = 1, header = TRUE)
gun_ownership=data.frame(df[,1],df[,2],df[,3],df[,4])
colnames(gun_ownership)<-c('State','Number_surveyed','Num.gunowned','Num.gunowned.percent')

# making dataframe for states with less gun ownership rate
low=data.frame(gun_ownership[order(gun_ownership$Num.gunowned.percent),'State'][1:10])
low$Ownershiprate='States with low gun ownership rate'

# making dataframe for states with high gun ownership rate
high=data.frame(gun_ownership[order(-gun_ownership$Num.gunowned.percent),'State'][1:10])
high$Ownershiprate='States with high gun ownership rate'
colnames(high)[1]<-'State'
colnames(low)[1]<-'State'

# combining rows of states with high and low gun ownership rates into a dataframe
highlow<-rbind(high,low)
highlow$State<-str_replace_all(highlow$State,"[*]","")

# statewise firearm suicides
files <- list.files(path='/Users/preethiranganathan/Documents/Santa Clara/data viz/indiv proj/statewise_gunsuicide',full.names = TRUE, pattern = ".csv")
d=data.frame()
for(i in 1:length(files)){
  d=rbind(read.table(files[i],sep=',',header=TRUE),d)
}
state_suicide=data.frame(d[,3],d[,9],d[,10])
state_suicide=unique(state_suicide)
colnames(state_suicide)=c('State','Deaths','Population')
# statewise firearm suicides per 100K
state_suicide$Deathsper100K=state_suicide$Deaths/state_suicide$Population*100000
state_suicide$Death_type ='Suicides'


# statewise firearm homicides
files <- list.files(path='/Users/preethiranganathan/Documents/Santa Clara/data viz/indiv proj/statewise_gunhomicide',full.names = TRUE, pattern = ".csv")
d=data.frame()
for(i in 1:length(files)){
  d=rbind(read.table(files[i],sep=',',header=TRUE),d)
}
state_homicide=data.frame(d[,3],d[,9],d[,10])
state_homicide=unique(state_homicide)
colnames(state_homicide)=c('State','Deaths','Population')

# statewise non-firearm suicides per 100K
state_homicide$Deathsper100K=state_homicide$Deaths/state_homicide$Population*100000
state_homicide$Death_type ='Homicides'

state_deaths=rbind(state_homicide,state_suicide)

ownership_deaths=inner_join(state_deaths,highlow,by='State')
```

    ## Warning: Column `State` joining factor and character vector, coercing into
    ## character vector

``` r
ggplot(ownership_deaths, aes(Ownershiprate, Deathsper100K, fill=Death_type)) +geom_col(position ='dodge')+ylim(0,14)+ ggtitle('States with the most guns report the most firearm homicides and suicides') + labs(x='',y = "Deaths per 100,000 people")+ theme(panel.grid.major = element_blank(), panel.grid.minor = element_blank(), panel.background = element_blank(),  axis.line = element_line(colour = "black"), plot.title = element_text( size=10), axis.title= element_text( size=8), legend.title= element_text(size=8))+ scale_fill_manual(name = "Death Type",values = c("#F8766D", "#00BFC4"))
```

![](Final_indiv_project_files/figure-gfm/Redesigned%20Final%20Claim%203-1.png)<!-- -->

<sup>Sources: N.C. State Center for Health Statistics-
<http://www.washingtonpost.com/wp-srv/health/interactives/guns/ownership.html?noredirect=on>,
Gun control laws - <https://www.statefirearmlaws.org/table.html></sup>

This chart clearly shows that death rates are higher for states with
high gun ownership rate compared to states with low gun ownership rates.

Contrasting colors are used here to just show comparison and it doesn’t
convey any meaning, in
particular.

## Deceptive product:

### Deceptive Claim 1: Homicide rates have declined over years while the firearm homicide rates have not (there is no increasing/decreasing trend over years).

#### Actual Argument:

Firearm and non-firearm homicide rates have declined over the
years.(Chart 9)

#### Actual Plot (1981-2016):

``` r
#Firearm Homicide data files from 1981 to 2015
firearmhomicidefiles <- list.files(path='~/Documents/Santa Clara/data viz/indiv proj/homicide',full.names = TRUE, pattern = ".csv")
d=data.frame()
for(i in 1:length(firearmhomicidefiles)){
  d=rbind(read.table(firearmhomicidefiles[i],sep=',',header=TRUE),d)
}
firearm_homicide=data.frame(d[,6],d[,9],d[,10])
firearm_homicide=unique(firearm_homicide)
colnames(firearm_homicide)<- c('Year','Deaths','Population')
firearm_homicide$Homicide_type='Firearm'

#Non-Firearm Homicide data files from 1981 to 2015
nonfirearmhomicidefiles <- list.files(path='~/Documents/Santa Clara/data viz/indiv proj/non-firearm-homicides',full.names = TRUE, pattern = ".csv")
d=data.frame()
for(i in 1:length(nonfirearmhomicidefiles)){
  d=rbind(read.table(nonfirearmhomicidefiles[i],sep=',',header=TRUE),d)
}
nonfirearm_homicides=data.frame(d[,7],d[,9],d[,10])
nonfirearm_homicides=unique(nonfirearm_homicides)
colnames(nonfirearm_homicides)<- c('Year','Deaths','Population')
nonfirearm_homicides$Homicide_type='Non-Firearm'

#Merge and normalized
homicides=merge(firearm_homicide, nonfirearm_homicides ,by.x='Year',by.y='Year',all=TRUE)
homicides=data.frame(homicides[,1],homicides[,2],homicides[,3],homicides[,4])
colnames(homicides)<-c('Year','Firearm','Population','Nonfirearm')
homicides$Firearm_norm<-(homicides$Firearm/homicides$Population)*100000
homicides$NonFirearm_norm<-(homicides$Nonfirearm/homicides$Population)*100000

#Combining firearm and non-firearm homicides
homicides1=rbind(firearm_homicide,nonfirearm_homicides)
homicides1$norm<-(homicides1$Deaths/homicides1$Population)*100000

ggplot(homicides1) +geom_line(aes(Year, norm,color=Homicide_type ))+ggtitle('Firearm and Non-Firearm homicide rates have declined over the years')+theme(panel.grid.major = element_blank(), panel.grid.minor = element_blank(), panel.background = element_blank(), axis.line = element_line(colour = "black"), plot.title = element_text( size=10),axis.title= element_text( size=9),legend.title= element_text( size=9))+ labs(x='Year',y = "Number of homicides per 100,000 people")+ scale_x_continuous(breaks=seq(1981,2017,3))+ coord_fixed(ratio = 4)+ guides(col=guide_legend(title="Homicide type"))
```

![](Final_indiv_project_files/figure-gfm/Actual%20DClaim%201-1.png)<!-- -->

<sup>Source: Centers for Disease Control and Prevention
-<https://webappa.cdc.gov/sasweb/ncipc/mortrate10_us.html></sup>

As we are more interested in the homicide rate trend, the plot is
smoothened to see the clear declining trend of homicide
rates.

#### Actual plot (1981-2016 -Smoothened):

``` r
ggplot(homicides1) +geom_smooth(aes(Year, norm,color=Homicide_type), se=FALSE)+ggtitle('Firearm and Non-Firearm homicide rates have declined over the years')+theme(panel.grid.major = element_blank(), panel.grid.minor = element_blank(), panel.background = element_blank(), axis.line = element_line(colour = "black"), plot.title = element_text( size=10),axis.title= element_text( size=8),legend.title= element_text( size=9))+ labs(x='Year',y = "Number of homicides per 100,000 people")+ scale_x_continuous(breaks=seq(1981,2017,3))+coord_fixed(ratio = 4) +guides(col=guide_legend(title="Homicide type"))
```

    ## `geom_smooth()` using method = 'loess'

![](Final_indiv_project_files/figure-gfm/Actual%20DClaim%201%20cont..-1.png)<!-- -->

<sup>Source: Centers for Disease Control and
Prevention-<https://webappa.cdc.gov/sasweb/ncipc/mortrate10_us.html></sup>

To explain the importance of gun violence in the US, it is better, if we
show the audience that the gun violence has increased over the years
instead of showing the opposite.

Hence, I replicated the plot and it showed the same trend as in the data
product. To make the main argument more compelling, I decided to pick up
just the increasing trend. But there is no increasing trend in homicides
(except during 2015 and 2016, which is very minimal).

So, I decided to limit the time period which has a constant trend
(neither increasing nor decreasing) of homicide rate. It would have been
a lot better if we have shown increasing trend of homicide rates.
Unfortunately, we don’t have such data.

Note that, the homicides does not include deaths inflicted by the police
or other law-enforcing agents in the course of arresting or attempting
to arrest lawbreakers.

In all the plots below, related to the claim, contrasting colors are
used just to show a difference between firearm and non-firearm
homicides. The colors, themselves, do not convey any meaning.

#### Final Version Deceptive plot:

The first and final version of deceptive plot doesn’t have much
difference except the color of the plot, axis and label font (to make it
uniform across all plots). Hence, didn’t include the first version
again.

``` r
homcides_cut=homicides1[homicides1$Year>2002,]

ggplot(homcides_cut) +geom_line(aes(Year, norm,color=Homicide_type ))+ggtitle('Non-firearm homicide rates have declined over years while firearm homicide rates have not')+theme(panel.grid.major = element_blank(), panel.grid.minor = element_blank(), panel.background = element_blank(),  axis.line = element_line(colour = "black"), plot.title = element_text( size=10),axis.title= element_text( size=9),legend.title= element_text( size=9))+ labs(x='Year',y = "Number of homicides per 100,000 people")+ scale_x_continuous(breaks=seq(2003,2017,1))+coord_fixed(ratio = 2) +guides(col=guide_legend(title="Homicide type"))
```

![](Final_indiv_project_files/figure-gfm/Final%20Version%20DClaim%201-1.png)<!-- -->

<sup> Source: Centers for Disease Control and Prevention-
-<https://webappa.cdc.gov/sasweb/ncipc/mortrate10_us.html></sup>

The plot is smoothened below to see clearly that there is no
increasing/decreasing homicide
trend.

#### Deceptive plot(Smoothened):

``` r
ggplot(homcides_cut) +geom_smooth(aes(Year, norm,color=Homicide_type), se=FALSE)+ ggtitle('Non-firearm homicide rates have declined over years while firearm homicide rates have not')+theme(panel.grid.major = element_blank(), panel.grid.minor = element_blank(), panel.background = element_blank(), axis.line = element_line(colour = "black"), plot.title = element_text( size=10),axis.title= element_text( size=8), legend.title= element_text( size=9))+ labs(x='Year',y = "Number of homicides per 100,000 people")+ scale_x_continuous(breaks=seq(2003,2017,1))+ coord_fixed(ratio = 2)+ guides(col=guide_legend(title="Homicide type"))
```

    ## `geom_smooth()` using method = 'loess'

![](Final_indiv_project_files/figure-gfm/Final%20Version%20DClaim%201%20cont..-1.png)<!-- -->

<sup>Source: Centers for Disease Control and Prevention-
-<https://webappa.cdc.gov/sasweb/ncipc/mortrate10_us.html></sup>

### Deceptive Claim 2: Tighter gun control laws does not reduce the number of gun-related deaths.

#### Chart from Vox:

``` r
img <- readPNG( '/Users/preethiranganathan/Documents/Santa Clara/data viz/indiv proj/Image8.png',native=TRUE)
plot.new() 
rasterImage(img,0,0,1,1)
```

![](Final_indiv_project_files/figure-gfm/Original%20DClaim%202-1.png)<!-- -->

<sup>Source: Vox
<https://www.vox.com/policy-and-politics/2017/10/2/16399418/us-gun-violence-statistics-maps-charts></sup>

This original chart is a geographical map. But it is not a good idea to
have this map as a warrant for expressing number of deaths. To validate
this argument, we just need to focus on states with tighter gun control
laws and states with less gun control laws. In this chart, tighter gun
control laws are defined as having atleast one firearm law designed to
protect children in the state. This might not be a real indicator of
strictness of gun control laws. Number of gun control laws that are
exercised in a state would be a good metric to measure the strictness of
gun control laws.

#### Actual Argument:

States with tighter gun control laws have fewer gun-related deaths.

#### Actual plot:

``` r
# Gun control laws for each state and year
gun_control=read.csv('~/Documents/Santa Clara/data viz/indiv proj/raw_data.csv',header=TRUE) 

# Gun control for 2014
gun_control=gun_control[gun_control[,2]==2014,]
gun_control=data.frame(gun_control[,1],gun_control[,136])
colnames(gun_control)<-c('State','Number_laws')

# Statewise gun death data -2014
gundeaths2014=read.xls('~/Documents/Santa Clara/data viz/indiv proj/Gun_Deaths_statewise.xlsx',header=TRUE, sheet=2)

# Filtering states with high number of gun control laws
highlaws=data.frame(gun_control[order(-gun_control$Number_laws),][1:10,])
lesslaws=data.frame(gun_control[order(gun_control$Number_laws),][1:10,])
highlaws$Number_GunControl_Laws='high'
lesslaws$Number_GunControl_Laws='low'
highlow=rbind(highlaws,lesslaws)

# Merging data sets
gun_control_deaths=merge(gundeaths2014, highlow ,by.x='STATE.NAME',by.y='State')
guncontrol_deaths=data.frame(gun_control_deaths[,2], gun_control_deaths[,3], gun_control_deaths[,4], gun_control_deaths[,6], gun_control_deaths[,10])
colnames(guncontrol_deaths)<-c("State",'population','Deathrate','Deaths_num','Number_of_gun_control_laws')
guncontrol_deaths$population<-as.numeric(str_replace_all(guncontrol_deaths$population,",",""))

ggplot(guncontrol_deaths, aes(reorder(State, -Deathrate), Deathrate , fill=Number_of_gun_control_laws)) +geom_col(position ='dodge') +ggtitle('States with tighter gun control laws have fewer firearm deaths')+theme_minimal()+theme(plot.title = element_text( size=10),axis.title= element_text( size=9),legend.title= element_text( size=9))+ labs(x='State',y = "Death rate in 2014")+ scale_fill_gradient(high='#00BFC4')+ guides(fill=guide_legend(title="Number of firearm control laws"))
```

![](Final_indiv_project_files/figure-gfm/Actual%20DClaim%202-1.png)<!-- -->

<sup>Sources: Centers for Disease Control and Prevention-
<https://webappa.cdc.gov/sasweb/ncipc/mortrate10_us.html> , <br />State
Firearm laws- <https://www.statefirearmlaws.org/table.html></sup>

Here, I decided to go with scale gradient bar chart(continuous colour
scales) as the metric chosen is the number of gun laws in a state. So,
it is good to show a comparison of deaths for states with diifferent
number of gun laws.

Note that, I have retained the grid in the charts for this claim, since
in bar charts, it is easier to draw comparison with grids.

#### Deceptive Plot:

This is one of the main claims made by the data product. So, I picked
this chart and made a deceptive version out of it.

I picked the states with high gun control laws and states with less gun
control laws to see a clear difference in gun deaths between states with
high gun control laws and low gun control laws. Here, I normalized the
number of deaths in each state per 100,000 people so that the population
of each state is taken into consideration. I also noticed that death
rate is not dependent on population in this chart.

Hence, I decided to make a deceptive chart without normalizing for
population ie.,I made y axis as raw number of deaths, not death rate per
100,000 people. As I expected, the chart showed that states with high
gun control laws has no correlation with gun deaths.

It would have been better, if I had picked few states where gun deaths
are prevalent and plotted a time trend of change in number of control
laws and change in gun deaths over years. There could be numerous
factors in each state, which could cause an increase in gun deaths. By
comparing gun deaths of one state across different years, we control for
other factors causing gun deaths in different states.

Unfortunately, that kind of time series data for every state is not
available. Hence, I have considered statewise number of gun control laws
and gun deaths in
2014.

``` r
ggplot(guncontrol_deaths, aes(reorder(State, -Deaths_num), Deaths_num , fill=Number_of_gun_control_laws)) + geom_col(position ='dodge') + ggtitle('Tighter gun control laws does not reduce the number of firearm deaths')+ theme_minimal()+ theme(plot.title = element_text(size=10), axis.title= element_text( size=9), legend.title= element_text(size=9))+ labs(x='State',y = "Number of deaths in 2014")+ scale_fill_gradient(high='#00BFC4')+ guides(fill=guide_legend(title="Number of firearm control laws"))
```

![](Final_indiv_project_files/figure-gfm/DClaim%202-1.png)<!-- -->

<sup>Sources: Centers for Disease Control and Prevention-
<https://webappa.cdc.gov/sasweb/ncipc/mortrate10_us.html> , <br />State
Firearm laws- <https://www.statefirearmlaws.org/table.html></sup>

I have just changed the color of the bars to the uniform color used
throughout the chart, added the source and removed the background from
the first version. These are the only changes to the chart. Hence, not
including the first version.

### Deceptive Claim 3: Restricting access to firearms can save lives.

As the number of firearm control laws has increased in the US over
years, firearm violence has reduced. New legal restrictions on owning
and purchasing firearms led to a drop in gun violence.

This argument is from the data product, but this is also deceptive.

#### Actual Argument:

The actual argument (suggested by me) is that restricting access to guns
has not saved lives. Gun violence has increased as the number of gun
control laws has increased over years.

#### Actual plot:

The entire data product is just focussing on the homicide rates or
suicides rates seperately, sometimes both. But, it never considered the
number of gun injuries. So, I calculated the total firearam casualties
as a sum of gun homicides, suicides and non-fatal injuries.

``` r
# Non-fatal gun injury
gun_injuryfiles <- list.files(path='~/Documents/Santa Clara/data viz/indiv proj/firearm_injuries',full.names = TRUE, pattern = ".csv")
d=data.frame()
for(i in 1:length(gun_injuryfiles)){
  d=rbind(read.table(gun_injuryfiles[i],sep=',',header=TRUE),d)
}
gun_injury=data.frame(d[,4],d[,7])
colnames(gun_injury)<-c('Year','Number_injuries')
gun_injury=gun_injury[gun_injury$Year>2000&gun_injury$Year<2015,]
gun_injury$Number_injuries=as.integer(str_replace_all(unfactor(gun_injury$Number_injuries),',',''))

# Gun homicides
firearmhomicidefiles <- list.files(path='~/Documents/Santa Clara/data viz/indiv proj/homicide',full.names = TRUE, pattern = ".csv")
d=data.frame()
for(i in 1:length(firearmhomicidefiles)){
  d=rbind(read.table(firearmhomicidefiles[i],sep=',',header=TRUE),d)
}
firearm_homicide=data.frame(d[,6],d[,9],d[,10])
firearm_homicide=unique(firearm_homicide)
colnames(firearm_homicide)<- c('Year','Homicides','Population')
firearm_homicide=firearm_homicide[firearm_homicide$Year>2000&gun_injury$Year<2015,]

# Gun suicides
suicidefiles <- list.files(path='~/Documents/Santa Clara/data viz/indiv proj/firearm_suicide',full.names = TRUE, pattern = ".csv")
d=data.frame()
for(i in 1:length(suicidefiles)){
  d=rbind(read.table(suicidefiles[i],sep=',',header=TRUE),d)
}
suicide=data.frame(d[,6],d[,9])
suicide=unique(suicide)
colnames(suicide)<- c('Year','Suicides')
suicide=suicide[suicide$Year>2000&gun_injury$Year<2015,]

## Total firearam casualties as a sum of gun homicides, suicides and non-fatal injuries
gun_casualties<-merge(firearm_homicide,suicide,by.x='Year',by.y='Year')
gun_casualties<-merge(gun_casualties,gun_injury,by.x='Year',by.y='Year')
gun_casualties$Total_casualties<-gun_casualties$Homicides+gun_casualties$Suicides+gun_casualties$Number_injuries
gun_casualties$Total_casualties_rate<-(gun_casualties$Total_casualties/gun_casualties$Population)*100000
gun_casualties$Homicide_rate<-(gun_casualties$Homicides)*100000/gun_casualties$Population 

#Gun control laws vs Gun Violence over years
gun_control=read.csv('~/Documents/Santa Clara/data viz/indiv proj/raw_data.csv',header=TRUE) 
gun_control=data.frame(gun_control[,2],gun_control[,136])
colnames(gun_control)<-c('Year','Number_laws')
gun_control=gun_control %>% group_by(Year) %>% summarize(Number_laws=sum(Number_laws))

homicides_control=merge(gun_casualties, gun_control ,by.x='Year',by.y='Year',all=TRUE)
homicides_control=homicides_control[complete.cases(homicides_control),]


p10=ggplot(homicides_control) +geom_line(aes(Year, Total_casualties_rate ))+theme(panel.grid.major = element_blank(), panel.grid.minor = element_blank(), panel.background = element_blank(),axis.line = element_line(colour = "black"),axis.title= element_text( size=9))+ labs(x='Year',y = "# of deaths per 100,000 people")+ scale_x_continuous(breaks=seq(2001,2014,1)) +coord_fixed(ratio = 0.515)

p11=ggplot(homicides_control) +geom_line(aes(Year, Number_laws ))+ggtitle(' Restricting access to firearms does not help reduce gun violence in the United States')+theme(panel.grid.major = element_blank(), panel.grid.minor = element_blank(), panel.background = element_blank(),axis.line = element_line(colour = "black"),plot.title = element_text( size=11),axis.title= element_text(size=9))+ labs(x='Year',y = "# of gun laws") + scale_x_continuous(breaks=seq(2001,2014,1))

ggarrange(p11, p10 + font("x.text", size = 10),
                    ncol = 1, nrow = 2)
```

![](Final_indiv_project_files/figure-gfm/Actual%20DClaim%203-1.png)<!-- -->

<sup>Sources: Centers for Disease Control and Prevention-
<https://webappa.cdc.gov/sasweb/ncipc/mortrate10_us.html> , <br />State
Firearm laws- <https://www.statefirearmlaws.org/table.html></sup>

This plot clearly shows that there has been an increasing trend of gun
casualties over years. We could see that death rate increases as the
number of gun laws increases in the US over years.

#### Deceptive plot:

The deceptive argument presented in the data product did not take into
account, the total number of firearm violence as a sum of gun homicides,
suicides and non-fatal injuries.

The decrease in homicide rate could be due to improved medical
facilities and emergency services in the recent years.
<https://www.umass.edu/newsoffice/article/research-finds-us-murder-rate-suppressed-improved-emergency-medical-response>

This could be verified by importing a Emergency Medical Service (EMS)
dataset, and checking the trend to correlate with decrease in homicide
rate.

``` r
p9=ggplot(homicides_control) +geom_line(aes(Year, Homicide_rate ))+theme(panel.grid.major = element_blank(), panel.grid.minor = element_blank(), panel.background = element_blank(),axis.line = element_line(colour = "black"),axis.title= element_text( size=9))+ labs(x='Year',y = "# of deaths per 100,000 people")+ scale_x_continuous(breaks=seq(2001,2014,1))+ coord_fixed(ratio = 3)

p11=ggplot(homicides_control) +geom_line(aes(Year, Number_laws ))+ggtitle('Restricting access to firearms can save lives in the United States')+theme(panel.grid.major = element_blank(), panel.grid.minor = element_blank(), panel.background = element_blank(),axis.line = element_line(colour = "black"),plot.title = element_text( size=11),axis.title= element_text(size=9))+ labs(x='Year',y = "# of gun laws") + scale_x_continuous(breaks=seq(2001,2014,1))

ggarrange(p11, p9 + font("x.text", size = 10),
                    ncol = 1, nrow = 2)
```

![](Final_indiv_project_files/figure-gfm/Final%20version%20DClaim%203-1.png)<!-- -->

<sup>Sources: Centers for Disease Control and Prevention-
<https://webappa.cdc.gov/sasweb/ncipc/mortrate10_us.html> ,<br /> State
Firearm laws- <https://www.statefirearmlaws.org/table.html></sup>

I have just changed the color of the curves to black (as there was no
necessity to include colors in it), added the source and change the
fonts, from the first version. Otherwise, I made no changes to the
chart. Hence, not including the first version.
