- 👋 Hi, I’m @mgorce4 or toast
- 👀 I’m interested in art and music
- 🌱 I’m currently learning java and javafx
- 📫 How to reach me : insta: @grc._.max discord: snor_lax13
- 😄 Pronouns: he/they

![Alt Text](https://media.giphy.com/media/vFKqnCdLPNOKc/giphy.gif)

library(httr)
library(ggplot2)

add_cat <- function(width = 400, height = 400){
  r <- GET(paste("http://theoldreader.com/kittens", width, height, sep = "/"))
  stop_for_status(r)
  img <- content(r)
  bw <- 0.2989*img[,,1] + 0.5870*img[,,2] + 0.1140*img[,,3]
  lighter <- bw + (0.7 * (1-bw))
  annotation_raster(lighter, xmin=-Inf, xmax=Inf, ymin=-Inf, ymax=Inf)
}

ggplot(mpg, aes(cty, hwy)) +
  add_cat() +
  geom_point()
