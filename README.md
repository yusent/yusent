```haskell
module MySelf where

type Skill = String

data Profile = Profile
  { name :: String
  , mainSkills :: [Skill]
  }

instance Show Profile where
  show p = unlines
         $ ("Hi! I'm " ++ name p ++ " and my main skills are:")
         : (bulletify <$> mainSkills p)

main :: IO ()
main = print mySelf

mySelf :: Profile
mySelf = Profile "Yus"
  [ "Haskell"
  , "Ruby"
  , "JavaScript"
  , "Rails"
  , "React"
  , "React Native"
  ]

bulletify :: String -> String
bulletify = ('-' :) . (' ' :)
```
