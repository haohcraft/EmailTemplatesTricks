#set($bgcolor="#f6f6f6")
#set($color-orange="#e67e22")
#set($color-blue="#1a67b2")
#set($color-white="#ffffff")
#set($color-grey="#dfdfdf")
#set($color-boldblack="#282828")
#set($font-family="arial")
#set($border-bottom="1px #c1c1c1 solid")
#set($border-top="1px #c1c1c1 solid")
##DATA INPUT
##Snippet
#set ($snippet = "Huge discounts on hotels, vacation packages, car rentals, and more!")
## Engaged user?
#set($engaged=${is_engaged})
## Email subject title
#set($subject = $snippet)
#if ($engaged == "true")
	#set($subject="${feature_fare_depature_city} Flight ${feature_fare_price} | ${bbdndeal_destination_0} ${bbdndeal_type_0} ${bbdndeal_price_0} | ${bbdndeal_destination_1} ${bbdndeal_type_1} ${bbdndeal_price_1}")
#else
	#if (${feature_story_title})
		#if (${feature_story_title} != "")
			#set($subject=${feature_story_title})
		#end
	#end
#end
## Featured story
##
#if (${feature_story_url})
	#set($feature_story_url=${feature_story_url})
#else
	#set($feature_story_url = "")
#end
#set($feature_story_title=${feature_story_title})
#set($feature_story_img_url=${feature_story_image_url})
#set($feature_story_img_alt=${feature_story_image_alt})
#set($feature_story_summary=${feature_story_summary})
## Featured fare
##
#if (${feature_fare_depature_city})
	#set($feature_fare_depature_city=${feature_fare_depature_city})
#else
	#set($feature_fare_depature_city = "")
#end
#set($feature_fare_arrival_city=${feature_fare_arrival_city})
#set($feature_fare_depature_airport_code=${feature_fare_depature_airport_code})
#set($feature_fare_arrival_airport_code=${feature_fare_arrival_airport_code})
#set($feature_fare_price=${feature_fare_price})
#set($feature_fare_url="http://rd.bookingbuddy.com/?r=i17746956n${newsletter_id}&u=${tracking_code}&nltv=${nltv}&fare_id=${feature_fare_id}&departure_city=${feature_fare_depature_airport_code}&arrival_city=${feature_fare_arrival_airport_code}&ns=1&dfnl=1")
#set($feature_fare_image_url=${feature_fare_image_url})
##Hotel Module Image
#set($hotel_module_img="Hotel_Module" + ${hotel_module_img_number} + ".jpg")
##BBDN Deal
##
## Module 2: 3 deals
#if (${bbdndeal_destination_0})
	#set($bbdndeal_destination_0=${bbdndeal_destination_0})
#else
	#set($bbdndeal_destination_0 = "")
#end
#set($bbdndeal_type_0=${bbdndeal_type_0})
#set($bbdndeal_title_0=${bbdndeal_title_0})
#set($bbdndeal_source_0=${bbdndeal_source_0})
#set($bbdndeal_price_0=${bbdndeal_price_0})
#set($bbdndeal_percentoff_0=${bbdndeal_percentoff_0})
#set($bbdndeal_url_0=${bbdndeal_url_0})
#set($bbdndeal_imageurl_0=${bbdndeal_imageurl_0})
#if (${bbdndeal_destination_1})
	#set($bbdndeal_destination_1=${bbdndeal_destination_1})
#else
	#set($bbdndeal_destination_1 = "")
#end
#set($bbdndeal_type_1=${bbdndeal_type_1})
#set($bbdndeal_title_1=${bbdndeal_title_1})
#set($bbdndeal_source_1=${bbdndeal_source_1})
#set($bbdndeal_price_1=${bbdndeal_price_1})
#set($bbdndeal_percentoff_1=${bbdndeal_percentoff_1})
#set($bbdndeal_url_1=${bbdndeal_url_1})
#set($bbdndeal_imageurl_1=${bbdndeal_imageurl_1})
#if (${bbdndeal_destination_2})
	#set($bbdndeal_destination_2=${bbdndeal_destination_2})
#else
	#set($bbdndeal_destination_2 = "")
#end
#set($bbdndeal_type_2=${bbdndeal_type_2})
#set($bbdndeal_title_2=${bbdndeal_title_2})
#set($bbdndeal_source_2=${bbdndeal_source_2})
#set($bbdndeal_price_2=${bbdndeal_price_2})
#set($bbdndeal_percentoff_2=${bbdndeal_percentoff_2})
#set($bbdndeal_url_2=${bbdndeal_url_2})
#set($bbdndeal_imageurl_2=${bbdndeal_imageurl_2})
##
## Module 3: 3 deals
#if (${bbdndeal_destination_3})
	#set($bbdndeal_destination_3=${bbdndeal_destination_3})
#else
	#set($bbdndeal_destination_3 = "")
#end
#set($bbdndeal_type_3=${bbdndeal_type_3})
#set($bbdndeal_title_3=${bbdndeal_title_3})
#set($bbdndeal_source_3=${bbdndeal_source_3})
#set($bbdndeal_price_3=${bbdndeal_price_3})
#set($bbdndeal_percentoff_3=${bbdndeal_percentoff_3})
#set($bbdndeal_url_3=${bbdndeal_url_3})
#set($bbdndeal_imageurl_3=${bbdndeal_imageurl_3})
#if (${bbdndeal_destination_4})
	#set($bbdndeal_destination_4=${bbdndeal_destination_4})
#else
	#set($bbdndeal_destination_4 = "")
#end
#set($bbdndeal_type_4=${bbdndeal_type_4})
#set($bbdndeal_title_4=${bbdndeal_title_4})
#set($bbdndeal_source_4=${bbdndeal_source_4})
#set($bbdndeal_price_4=${bbdndeal_price_4})
#set($bbdndeal_percentoff_4=${bbdndeal_percentoff_4})
#set($bbdndeal_url_4=${bbdndeal_url_4})
#set($bbdndeal_imageurl_4=${bbdndeal_imageurl_4})

#if (${bbdndeal_destination_5})
	#set($bbdndeal_destination_5=${bbdndeal_destination_5})
#else
	#set($bbdndeal_destination_5 = "")
#end
#set($bbdndeal_type_5=${bbdndeal_type_5})
#set($bbdndeal_title_5=${bbdndeal_title_5})
#set($bbdndeal_source_5=${bbdndeal_source_5})
#set($bbdndeal_price_5=${bbdndeal_price_5})
#set($bbdndeal_percentoff_5=${bbdndeal_percentoff_5})
#set($bbdndeal_url_5=${bbdndeal_url_5})
#set($bbdndeal_imageurl_5=${bbdndeal_imageurl_5})
##
## Module 4: 3 deals
#if (${bbdndeal_destination_6})
	#set($bbdndeal_destination_6=${bbdndeal_destination_6})
#else
	#set($bbdndeal_destination_6 = "")
#end
#set($bbdndeal_type_6=${bbdndeal_type_6})
#set($bbdndeal_title_6=${bbdndeal_title_6})
#set($bbdndeal_source_6=${bbdndeal_source_6})
#set($bbdndeal_price_6=${bbdndeal_price_6})
#set($bbdndeal_percentoff_6=${bbdndeal_percentoff_6})
#set($bbdndeal_url_6=${bbdndeal_url_6})
#set($bbdndeal_imageurl_6=${bbdndeal_imageurl_6})
#if (${bbdndeal_destination_7})
	#set($bbdndeal_destination_7=${bbdndeal_destination_7})
#else
	#set($bbdndeal_destination_7 = "")
#end
#set($bbdndeal_type_7=${bbdndeal_type_7})
#set($bbdndeal_title_7=${bbdndeal_title_7})
#set($bbdndeal_source_7=${bbdndeal_source_7})
#set($bbdndeal_price_7=${bbdndeal_price_7})
#set($bbdndeal_percentoff_7=${bbdndeal_percentoff_7})
#set($bbdndeal_url_7=${bbdndeal_url_7})
#set($bbdndeal_imageurl_7=${bbdndeal_imageurl_7})
#if (${bbdndeal_destination_8})
	#set($bbdndeal_destination_8=${bbdndeal_destination_8})
#else
	#set($bbdndeal_destination_8 = "")
#end
#set($bbdndeal_type_8=${bbdndeal_type_8})
#set($bbdndeal_title_8=${bbdndeal_title_8})
#set($bbdndeal_source_8=${bbdndeal_source_8})
#set($bbdndeal_price_8=${bbdndeal_price_8})
#set($bbdndeal_percentoff_8=${bbdndeal_percentoff_8})
#set($bbdndeal_url_8=${bbdndeal_url_8})
#set($bbdndeal_imageurl_8=${bbdndeal_imageurl_8})
##
## Module 5: 8 flights
#if (${faredeal_arrival_city_0})
	#set($faredeal_arrival_city_0=${faredeal_arrival_city_0})
#else
	#set($faredeal_arrival_city_0 = "")
#end
#set($faredeal_arrival_airport_0=${faredeal_arrival_airport_0})
#set($faredeal_price_0=${faredeal_price_0})
#set($faredeal_id_0=${faredeal_id_0})
#set($faredeal_url_0="http://rd.bookingbuddy.com/?r=i17746956n${newsletter_id}&u=${tracking_code}&nltv=${nltv}&fare_id=${faredeal_id_0}&departure_city=${dep_airport_code}&arrival_city=${faredeal_arrival_airport_0}&ns=1&dfnl=1")
#if (${faredeal_arrival_city_1})
	#set($faredeal_arrival_city_1=${faredeal_arrival_city_1})
#else
	#set($faredeal_arrival_city_1 = "")
#end
#set($faredeal_arrival_airport_1=${faredeal_arrival_airport_1})
#set($faredeal_price_1=${faredeal_price_1})
#set($faredeal_id_1=${faredeal_id_1})
#set($faredeal_url_1="http://rd.bookingbuddy.com/?r=i17746956n${newsletter_id}&u=${tracking_code}&nltv=${nltv}&fare_id=${faredeal_id_1}&departure_city=${dep_airport_code}&arrival_city=${faredeal_arrival_airport_1}&ns=1&dfnl=1")

#if (${faredeal_arrival_city_2})
	#set($faredeal_arrival_city_2=${faredeal_arrival_city_2})
#else
	#set($faredeal_arrival_city_2 = "")
#end
#set($faredeal_arrival_airport_2=${faredeal_arrival_airport_2})
#set($faredeal_price_2=${faredeal_price_2})
#set($faredeal_id_2=${faredeal_id_2})
#set($faredeal_url_2="http://rd.bookingbuddy.com/?r=i17746956n${newsletter_id}&u=${tracking_code}&nltv=${nltv}&fare_id=${faredeal_id_2}&departure_city=${dep_airport_code}&arrival_city=${faredeal_arrival_airport_2}&ns=1&dfnl=1")
#if (${faredeal_arrival_city_3})
	#set($faredeal_arrival_city_3=${faredeal_arrival_city_3})
#else
	#set($faredeal_arrival_city_3 = "")
#end
#set($faredeal_arrival_airport_3=${faredeal_arrival_airport_3})
#set($faredeal_price_3=${faredeal_price_3})
#set($faredeal_id_3=${faredeal_id_3})
#set($faredeal_url_3="http://rd.bookingbuddy.com/?r=i17746956n${newsletter_id}&u=${tracking_code}&nltv=${nltv}&fare_id=${faredeal_id_3}&departure_city=${dep_airport_code}&arrival_city=${faredeal_arrival_airport_3}&ns=1&dfnl=1")
#if (${faredeal_arrival_city_4})
	#set($faredeal_arrival_city_4=${faredeal_arrival_city_4})
#else
	#set($faredeal_arrival_city_4 = "")
#end
#set($faredeal_arrival_airport_4=${faredeal_arrival_airport_4})
#set($faredeal_price_4=${faredeal_price_4})
#set($faredeal_id_4=${faredeal_id_4})
#set($faredeal_url_4="http://rd.bookingbuddy.com/?r=i17746956n${newsletter_id}&u=${tracking_code}&nltv=${nltv}&fare_id=${faredeal_id_4}&departure_city=${dep_airport_code}&arrival_city=${faredeal_arrival_airport_4}&ns=1&dfnl=1")

#if (${faredeal_arrival_city_5})
	#set($faredeal_arrival_city_5=${faredeal_arrival_city_5})
#else
	#set($faredeal_arrival_city_5 = "")
#end
#set($faredeal_arrival_airport_5=${faredeal_arrival_airport_5})
#set($faredeal_price_5=${faredeal_price_5})
#set($faredeal_id_5=${faredeal_id_5})
#set($faredeal_url_5="http://rd.bookingbuddy.com/?r=i17746956n${newsletter_id}&u=${tracking_code}&nltv=${nltv}&fare_id=${faredeal_id_5}&departure_city=${dep_airport_code}&arrival_city=${faredeal_arrival_airport_5}&ns=1&dfnl=1")
#if (${faredeal_arrival_city_6})
	#set($faredeal_arrival_city_6=${faredeal_arrival_city_6})
#else
	#set($faredeal_arrival_city_6 = "")
#end
#set($faredeal_arrival_airport_6=${faredeal_arrival_airport_6})
#set($faredeal_price_6=${faredeal_price_6})
#set($faredeal_id_6=${faredeal_id_6})
#set($faredeal_url_6="http://rd.bookingbuddy.com/?r=i17746956n${newsletter_id}&u=${tracking_code}&nltv=${nltv}&fare_id=${faredeal_id_6}&departure_city=${dep_airport_code}&arrival_city=${faredeal_arrival_airport_6}&ns=1&dfnl=1")
#if (${faredeal_arrival_city_7})
	#set($faredeal_arrival_city_7=${faredeal_arrival_city_7})
#else
	#set($faredeal_arrival_city_7 = "")
#end
#set($faredeal_arrival_airport_7=${faredeal_arrival_airport_7})
#set($faredeal_price_7=${faredeal_price_7})
#set($faredeal_id_7=${faredeal_id_7})
#set($faredeal_url_7="http://rd.bookingbuddy.com/?r=i17746956n${newsletter_id}&u=${tracking_code}&nltv=${nltv}&fare_id=${faredeal_id_7}&departure_city=${dep_airport_code}&arrival_city=${faredeal_arrival_airport_7}&ns=1&dfnl=1")
## MACROsssssss
##
## macro for module 1
#macro(feature_story, $feature_story_url,$feature_story_img_url,$feature_story_title,$feature_story_summary, $feature_story_img_alt)
#if ($feature_story_url != "")
<tr>
	<td bgcolor=$color-white style="border-bottom:$border-bottom;">
		<!-- image -->
		<table border="0" align="left" cellpadding="0" cellspacing="0" >
			<tbody>
				<tr>
					<td class="w240" align="center" width="250" height="165">
						<a href=$feature_story_url style="text-decoration:none;" target="_blank">
							<img src=$feature_story_img_url  alt=$feature_story_img_alt class="w240" width="250" height="165" border="0" style="display:block; width:250px; height: 165px;">
						</a>
					</td>
				</tr>
			</tbody>
		</table>
		<!-- spacing -->
		<table width="10" height="10" align="left" cellpadding="0" cellspacing="0" style="width=10px; height=1px;">
			<tbody>
				<tr>
					<td width="10" height="10"  style="width:10px;height:10px;">&nbsp;</td>
				</tr>
			</tbody>
		</table>
		<!-- content detail -->
		<table width="210" align="left" cellpadding="0" cellspacing="0" border="0">
			<tbody>
				<!-- spacing -->
				<tr>
					<td width="210" height="10" style="width:210px; height:10px;"></td>
				</tr>
				<!-- content title -->
				<tr>
					<td  align="left" style="font-family:$font-family; font-size:15px;color:#1656a5;">
						<a href=$feature_story_url  target="_blank" style="text-decoration: none;">
							<span style="text-decoration:none; font-family:$font-family; font-size:15px;color:#1656a5;">$feature_story_title</span>
						</a>
					</td>
				</tr>
				<!--content summary -->
				<tr>
					<td class="mobilehide" align="left" style="font-family:$font-family; font-size:14px;color:#282828; line-height:18px;">
						$feature_story_summary
					</td>
				</tr>
				<tr>
					<td class="mobileshow" width="210" height="20" style="width:210px; height:20px; display:none;"></td>
				</tr>
				<!-- Read More -->
				<tr>
					<td align="left" style="font-family:$font-family; font-weight:bold; font-size:14px;color:#1656a5;">
						<a href=$feature_story_url target="_blank"  style="text-decoration: none;">
							<span style="text-decoration:none; font-family:$font-family; font-weight:bold; font-size:14px;color:#1656a5;">read more »</spam>
						</a>
					</td>
				</tr>
			</tbody>
		</table>
		<!-- spacing -->
		<table width="10" border="0" align="left" cellpadding="0" cellspacing="0">
			<tbody>
				<tr>
					<td width="10" height="10"  style="width:10px;height:10px;">&nbsp;</td>
				</tr>
			</tbody>
		</table>
	</td>
</tr>
#end
#end
#macro(feature_fare, $feature_fare_depature_city, $feature_fare_arrival_city, $feature_fare_depature_airport_code, $feature_fare_arrival_airport_code, $feature_fare_price, $feature_fare_url, $feature_fare_image_url)
#if ($feature_fare_depature_city != "")
<tr>
	<td bgcolor=$color-white style="border-bottom:$border-bottom;">
		<!-- image -->
		<table border="0" align="left" cellpadding="0" cellspacing="0">
			<tbody>
				<tr>
					<td align="center" width="165" height="110">
						<a href=$feature_fare_url style="text-decoration:none;" target="_blank">
							<img src=$feature_fare_image_url  alt="feature-image"  width="165" height="110" border="0" style="display:block; ">
						</a>
					</td>
				</tr>
			</tbody>
		</table>
		<!-- spacing -->
		<table width="10" height="10" border="0" align="left" cellpadding="0" cellspacing="0">
			<tbody>
				<tr>
					<td width="10" height="10" style="font-size: 1px; line-height: 10px;">&nbsp;</td>
				</tr>
			</tbody>
		</table>
		<!-- content detail -->
		<table width="220" height="110" align="left" cellpadding="0" cellspacing="0">
			<tbody>
				<!-- spacing -->
				<tr>
					<td width="100%" height="10" style="font-size: 1px; line-height: 10px;"></td>
				</tr>
				<!--cities -->
				<tr>
					<td align="left" style="font-family:$font-family; font-size:15px;color:#1656a5; line-height:20px;">
						<a href=$feature_fare_url  target="_blank"  style="text-decoration: none;">
							<span style="font-family:$font-family; font-size:15px;color:#1656a5; line-height:20px;">$feature_fare_depature_city to $feature_fare_arrival_city </span>
						</a>
					</td>
				</tr>
				<!-- spacing -->
				<tr>
					<td width="100%" height="5" style="font-size: 1px; line-height: 5px;"></td>
				</tr>
				<!-- airports -->
				<tr>
					<td align="left" style="font-family:$font-family; font-size:13px;color:#555555;">
						($feature_fare_depature_airport_code) to ($feature_fare_arrival_airport_code) 
					</td>
				</tr>
				<!-- Price -->
				<tr>
					<td align="left" style="font-family:$font-family; font-weight:bold; font-size:14px;color:#1656a5;">
						<!-- "from" -->
						<table align="left" >
							<!--  vertical spacing -->
							<tr>
								<td width="100%" height="10" style="font-size: 1px; line-height: 10px;"></td>
							</tr>
							<tr>
								<td  style="font-family: $font-family; font-size: 11px; color:#999999">
									<a href=$feature_fare_url  target="_blank"  style="text-decoration: none;">
										<span style="text-decoration:none; font-family:$font-family; font-size:11px;color:#999999;">from</span>
									</a>
								</td>
							</tr>		
						</table>
						<!-- rate -->
						<table align="left">
							<tr>
								<td  style="font-family: $font-family; font-size: 24px; color:$color-orange">
									<a href=$feature_fare_url  target="_blank"  style="text-decoration: none;">
										<span style="text-decoration:none; font-family:$font-family; font-size:24px;color:$color-orange;">$feature_fare_price</span>
									</a>
								</td>
							</tr>
						</table>
					</td>
				</tr>
			</tbody>
		</table>
	</td>
</tr>
#end
#end
## macro for module 2
#macro(display_bbdndeal_1, $bbdndeal_destination, $bbdndeal_type, $bbdndeal_title, $bbdndeal_source, $bbdndeal_price, $bbdndeal_url,$bbdndeal_imageurl, $is_top_border)
#if($bbdndeal_destination != "")
<tr>
	#if($is_top_border)
	<td bgcolor=$color-white style="border-bottom:$border-bottom; border-top:$border-top; " >
	#else
	<td bgcolor=$color-white style="border-bottom:$border-bottom; " >
	#end
		<!-- image -->
		<table border="0" align="left" cellpadding="0" cellspacing="0">
			<tbody>
				<tr>
					<td align="center" width="165" height="110">
						<a href=$bbdndeal_url style="text-decoration:none;" target="_blank">
							<img src=$bbdndeal_imageurl alt="feature-image" width="165" height="110" border="0" style="display:block; ">
						</a>
					</td>
				</tr>
			</tbody>
		</table>
		<!-- horizontal spacing -->
		<table border="0" align="left" cellpadding="0" cellspacing="0" style="width=10px; height=1px;">
			<tbody>
				<tr>
					<td width="10" height="1" style="width=10px; height=1px;">&nbsp;</td>
				</tr>
			</tbody>
		</table>
		<!-- content detail -->
		<table width="205" height="110" align="left" cellpadding="0" cellspacing="0">
			<!--  vertical spacing -->
			<tr>
				<td width="100%" height="10" style="font-size: 1px; line-height: 10px;"></td>
			</tr>
			<!-- content type -->
			<tr>
				<td align="left" style="font-family:$font-family; font-size:15px;color:#555555;">
					<a href=$bbdndeal_url  target="_blank"  style="text-decoration: none;">
						<span style="text-decoration:none; font-family:$font-family; font-size:15px;color:#555555;">$bbdndeal_destination $bbdndeal_type</span>
					</a>
				</td>
			</tr>
			<!-- content title -->
			<tr>
				<td align="left" style="font-family:$font-family; font-size:15px;color:#1656a5;font-weight: bold; line-height: 20px">
					<a href=$bbdndeal_url  target="_blank"  style="text-decoration: none;">
						<span style="text-decoration:none; font-family:$font-family; font-size:15px;color:#1656a5;font-weight: bold; line-height: 20px">$bbdndeal_title</span>
					</a>
				</td>
			</tr>
			<!--  vertical spacing -->
			<tr>
				<td width="100%" height="8" style="font-size: 1px; line-height: 8px;"></td>
			</tr>
			<!-- content source -->
			<tr>
				<td align="left" style="font-family:$font-family; font-size:13px;color:#999999;">
					<a href=$bbdndeal_url  target="_blank"  style="text-decoration: none;">
						<span style="text-decoration:none; font-family:$font-family; font-size:13px;color:#999999;">$bbdndeal_source</span>
					</a>

				</td>
			</tr>
		</table>
		<!-- content price -->
		<table width="90" align="right" cellpadding="0" cellspacing="0">
			<!--  vertical spacing -->
			<tr>
				<td width="90" height="20" style="font-size: 1px; line-height: 20px;"></td>
			</tr>
			<tr>
				<td>
					<!-- horizontal spacing -->
					<table width="5" height="1" border="0" align="right" cellpadding="0" cellspacing="0">
						<tbody>
							<tr>
								<td width="5" height="1" style="font-size: 1px; line-height: 1px;">&nbsp;</td>
							</tr>
						</tbody>
					</table>
					<table align="right">
						<tr>
							<td style="font-family: $font-family; font-size: 11px; color:#999999; text-align: right;">
								<a href=$bbdndeal_url  target="_blank" style="text-decoration:none;">
									<span style="text-decoration:none; font-family:$font-family; font-size:11px;color:#999999;">from</span>
								</a>
							</td>
						</tr>
						<tr>
							<td  style="font-family: $font-family; font-size: 24px; color:$color-orange">
								<a href=$bbdndeal_url  target="_blank" style="text-decoration:none;">
									<span style="text-decoration:none; font-family:$font-family; font-size:24px;color:$color-orange;">$bbdndeal_price</span>
								</a>
							</td>
						</tr>
					</table>
				</td>
			</tr>
		</table>
	</td>
</tr>
#end
#end
##
## macro for module 3
#macro(display_bbdndeal_2, $bbdndeal_destination, $bbdndeal_type, $bbdndeal_title, $bbdndeal_source, $bbdndeal_price, $bbdndeal_url)
#if($bbdndeal_destination != "")
<tr>
	<td bgcolor=$color-white style="border-bottom:$border-bottom; " >
		<!-- horizontal spacing -->
		<table width="15" height="1" border="0" align="left" cellpadding="0" cellspacing="0">
			<tbody>
				<tr>
					<td width="15" height="1" style="font-size: 1px; line-height: 1px;">&nbsp;</td>
				</tr>
			</tbody>
		</table>
		<!-- content detail -->
		<table width="340" align="left" cellpadding="0" cellspacing="0">
			<!--  vertical spacing -->
			<tr>
				<td width="100%" height="15" style="font-size: 1px; line-height: 15px;"></td>
			</tr>
			<!-- content type -->
			<tr>
				<td align="left" style="font-family:$font-family; font-size:15px;color:#555555;">
					<a href=$bbdndeal_url  target="_blank" style="text-decoration:none;">
						<span style="text-decoration:none; font-family:$font-family; font-size:15px;color:#555555;">$bbdndeal_destination $bbdndeal_type</span>
					</a>
				</td>
			</tr>
			<!-- content title -->
			<tr>
				<td align="left" style="font-family:$font-family; font-size:15px;color:#1656a5;font-weight: bold; line-height: 20px">
					<a href=$bbdndeal_url  target="_blank" style="text-decoration:none;">
						<span style="text-decoration:none; font-family:$font-family; font-size:15px;color:#1656a5;font-weight: bold; line-height: 20px">$bbdndeal_title</span>
					</a>
				</td>
			</tr>
			<!--  vertical spacing -->
			<tr>
				<td width="100%" height="10" style="font-size: 1px; line-height: 10px;"></td>
			</tr>
			<!-- content source -->
			<tr>
				<td align="left" style="font-family:$font-family; font-size:13px;color:#999999;">
					<a href=$bbdndeal_url  target="_blank" style="text-decoration:none;">
						<span style="text-decoration:none; font-family:$font-family; font-size:13px;color:#999999;">$bbdndeal_source</span>
					</a>
				</td>
			</tr>
			<!--  vertical spacing -->
			<tr>
				<td width="100%" height="3" style="font-size: 1px; line-height: 3px;"></td>
			</tr>
		</table>
		<!-- content price -->
		<table width="90" align="right" cellpadding="0" cellspacing="0">
			<!--  vertical spacing -->
			<tr>
				<td width="1" height="20" style="font-size: 1px; line-height: 20px;"></td>
			</tr>
			<tr>
				<td>
					<!-- horizontal spacing -->
					<table width="10" height="1" border="0" align="right" cellpadding="0" cellspacing="0">
						<tbody>
							<tr>
								<td width="10" height="1" style="font-size: 1px; line-height: 1px;">&nbsp;</td>
							</tr>
						</tbody>
					</table>
					<table align="right">
						<tr>
							<td  style="font-family: $font-family; font-size: 11px; color:#999999; text-align: right;">
								<a href=$bbdndeal_url  target="_blank" style="text-decoration:none; ">
									<span style="text-decoration:none; font-family:$font-family; font-size:11px;color:#999999;">from<span>
								</a>
							</td>
						</tr>
						<tr>
							<td  style="font-family: $font-family; font-size: 24px; color:$color-orange">
								<a href=$bbdndeal_url  target="_blank" style="text-decoration:none; ">
									<span style="text-decoration:none; font-family:$font-family; font-size:24px;color:$color-orange;">$bbdndeal_price<span>
								</a>
							</td>
						</tr>
					</table>
				</td>
			</tr>
		</table>
	</td>
</tr>
#end
#end
##
## macro for module 4
#macro(display_bbdndeal_3, $bbdndeal_destination, $bbdndeal_type, $bbdndeal_title, $bbdndeal_source, $bbdndeal_price, $bbdndeal_url)
#set($bbdndeal_type_icon=${bbdndeal_type}+"_Icon.png")
#if($bbdndeal_destination != "")
<tr>
	<td bgcolor=$color-white style="border-bottom:$border-bottom; " >
		<!-- Type icon -->
		<table border="0" align="left" cellpadding="0" cellspacing="0">
			<tbody>
				<tr>
					<td width="100%" height="15" style="font-size: 1px; line-height: 15px;"></td>
				</tr>
				<tr>
					#if ($bbdndeal_type == "Package")
						<td align="center" width="88" height="80">
							<img src="http://i.slimg.com/htmlemail/bb/ttd/$bbdndeal_type_icon" alt="type-icon" width="38" height="37" border="0" style="display:block; ">
						</td>
					#else
						<td align="center" width="88" height="80">
							<img src="http://i.slimg.com/htmlemail/bb/ttd/$bbdndeal_type_icon" alt="type-icon" width="38" height="22" border="0" style="display:block; ">
						</td>
					#end
				</tr>
			</tbody>
		</table>
		<!-- content detail -->
		<table width="240" align="left" cellpadding="0" cellspacing="0">
			<!--  vertical spacing -->
			<tr>
				<td width="100%" height="15" style="font-size: 1px; line-height: 15px;"></td>
			</tr>
			<!-- content type -->
			<tr>
				<td align="left" style="font-family:$font-family; font-size:15px;color:#555555;">
					<a href=$bbdndeal_url  target="_blank" style="text-decoration:none; ">
						<span  style="text-decoration:none; font-family:$font-family; font-size:15px;color:#555555;">$bbdndeal_destination $bbdndeal_type</span>
					</a>
				</td>
			</tr>
			<!-- content title -->
			<tr>
				<td align="left" style="font-family:$font-family; font-size:15px;color:#1656a5;font-weight: bold; line-height: 20px">
					<a href=$bbdndeal_url  target="_blank" style="text-decoration:none; ">
						<span style="text-decoration:none; font-family:$font-family; font-size:15px;color:#1656a5;font-weight: bold; line-height: 20px">$bbdndeal_title</span>
					</a>
				</td>
			</tr>
			<!--  vertical spacing -->
			<tr>
				<td width="100%" height="10" style="font-size: 1px; line-height: 10px;"></td>
			</tr>
			<!-- content source -->
			<tr>
				<td align="left" style="font-family:$font-family; font-size:13px;color:#999999;">
					<a href=$bbdndeal_url  target="_blank" style="text-decoration:none; ">
							<span style="text-decoration:none; font-family:$font-family; font-size:13px;color:#999999;">$bbdndeal_source<span>
					</a>
				</td>
			</tr>
			<!--  vertical spacing -->
			<tr>
				<td width="100%" height="3" style="font-size: 1px; line-height: 3px;"></td>
			</tr>
		</table> 
		<!-- content price -->
		<table width="90" align="right" cellpadding="0" cellspacing="0">
			<!--  vertical spacing -->
			<tr>
				<td width="100%" height="30" style="font-size: 1px; line-height: 30px;"></td>
			</tr>
			<tr>
				<td>
					<!-- horizontal spacing -->
					<table width="10" height="1" border="0" align="right" cellpadding="0" cellspacing="0">
						<tbody>
							<tr>
								<td width="10" height="1" style="font-size: 1px; line-height: 1px;">&nbsp;</td>
							</tr>
						</tbody>
					</table>
					<table align="right">
						<tr>
							<td  style="font-family: $font-family; font-size: 11px; color:#999999;text-align: right;">
								<a href=$bbdndeal_url  target="_blank" style="text-decoration:none; ">
									<span style="text-decoration:none; font-family:$font-family; font-size:11px;color:#999999;">from<span>
								</a>
							</td>
						</tr>
						<tr>
							<td  style="font-family: $font-family; font-size: 24px; color:$color-orange">
								<a href=$bbdndeal_url  target="_blank" style="text-decoration:none; ">
									<span style="text-decoration:none; font-family:$font-family; font-size:24px;color:$color-orange;">$bbdndeal_price<span>
								</a>
							</td>
						</tr>
					</table>
				</td>
			</tr>
		</table>
	</td>
</tr>
#end
#end
##
## macro for module 5
#macro(display_fare_deal, $faredeal_arrival_city, $faredeal_arrival_airport, $faredeal_price, $faredeal_id,$faredeal_url, $isGrey)
#if($faredeal_arrival_city != "")
<tr>
	#if ($isGrey)
		<td bgcolor="#dfdfdf" height="50">
	#else
		<td bgcolor=$color-white height="50" >
	#end
		<!-- horizontal spacing -->
		<table width="10" height="1" border="0" align="left" cellpadding="0" cellspacing="0">
			<tbody>
				<tr>
					<td width="10" height="1" style="font-size: 1px; line-height: 1px;">&nbsp;</td>
				</tr>
			</tbody>
		</table>
		<!-- content detail -->
		<table width="300" align="left" cellpadding="0" cellspacing="0">
			<!--  vertical spacing -->
			<tr>
				<td width="100%" height="10" style="font-size: 1px; line-height: 10px;"></td>
			</tr>
			<!-- content destination -->
			<tr>
				<td align="left" style="font-family:$font-family; font-size:16px;color:#282828;">
					<a href=$faredeal_url  target="_blank" style="text-decoration:none; ">
						<span style="text-decoration:none; font-family:$font-family; font-size:16px;color:#282828;">$faredeal_arrival_city ($faredeal_arrival_airport)</span>
					</a>
				</td>
			</tr>
			<!--  vertical spacing -->
			<tr>
				<td width="100%" height="10" style="font-size: 1px; line-height: 10px;"></td>
			</tr>
		</table>
		<!-- horizontal spacing -->
		<table width="10" height="1" border="0" align="right" cellpadding="0" cellspacing="0">
			<tbody>
				<tr>
					<td width="10" height="1" style="font-size: 1px; line-height: 1px;">&nbsp;</td>
				</tr>
			</tbody>
		</table>
		<!-- content price -->
		<table width="140" align="right" cellpadding="0" cellspacing="0">
			<!--  vertical spacing -->
			<tr>
				<td width="100%" height="10" style="font-size: 1px; line-height: 10px;"></td>
			</tr>
			<tr>
				<td>
					<table align="right">
						<tr>
							<td height="22" style="vertical-align:bottom;">
								<a href=$faredeal_url style="text-decoration:none;"  target="_blank" >
									<span style="text-decoration:none;font-family:$font-family; font-size:16px;color:$color-blue;">$faredeal_price RT »</span>
								</a>
							</td>
						</tr>
					</table>
					<table align="right" >
						<tr>
							<td height="20" style="font-family: $font-family; font-size: 11px; color:#999999; vertical-align:bottom;">
								from
							</td>
						</tr>
					</table>
				</td>
			</tr>
		</table>
	</td>
</tr>
#end
#end
MAIL FROM:<b-${tracking_code}-${mailing_id}-${newsletter_id}-${timestamp}@${sending_domain}>
RCPT TO:<${email_address}>
DATA
From: "${from_name}" <${from_address}>
To: "${first_name}" <${email_address}>
Subject: $subject
Reply-To: "${reply_to_name}" <${reply_to_address}>
Errors-To: b-${tracking_code}-${mailing_id}-${newsletter_id}-${timestamp}@${sending_domain}
Message-ID: <m-${tracking_code}-${mailing_id}-${newsletter_id}-${timestamp}@${sending_domain}>
List-ID: "${from_name}" <${from_address}>
X-RPCampaign: STM${site_abbreviation}${product_abbreviation}${newsletter_id}${timestamp}
Precedence: bulk
MIME-Version: 1.0
Content-Type: text/html; charset=utf-8

## Main Course
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
<html>
	<head>
		<meta http-equiv="Content-Type" content="text/html; charset=utf-8">
		<style type="text/css">
			table { border-collapse:collapse; mso-table-lspace:0pt; mso-table-rspace:0pt; } 
			  @media only screen and (max-device-width: 480px) {
			  *[class=mobileshow] { display:block !important;}
			  *[class=mobilehide] { display:none !important;}
		</style>
		<link rel="stylesheet" type="text/css" href="http://c.slimg.com/nlot/${tracking_code}/${newsletter_id}/${nltv}/bbnl_generic.css" />
	</head>

	<body >
		<table width="100%" cellpadding="0" cellspacing="0" border="0">
			<tbody>
				<td align="left" bgcolor=$bgcolor>
					<img src="http://i.slimg.com/nlot/${tracking_code}/${newsletter_id}/${nltv}/s.gif" border="0" hspace="0" vspace="0" width="1" height="1" align="right" />
					<table class="w480" width="480" style="width: 480px" border="0" cellpadding="0" cellspacing="0" bgcolor=$bgcolor align="center">
						<tbody>
							<!-- snippet -->
							<tr>
								<td height=20 style="font-family: $font-family; font-size:12px; color:$color-boldblack;">
									${snippet}
								</td>
							</tr>
							<!-- header -->
							<tr bgcolor="#ffffff">
								<td height="60" >
									<!-- spacing -->
									<table class="w5" width="1" height="0" border="0" align="left" cellpadding="0" cellspacing="0" style="height:1px;width:5px;">
										<tbody>
											<tr>
												<td width="5" height="1" style="font-size: 1px; line-height: 1px;">&nbsp;</td>
											</tr>
										</tbody>
									</table>
									<!-- icon -->
									<table width="126" border="0" align="left" valign="center" cellpadding="0" cellspacing="0" >
										<tbody>
											<tr>
												<td align="center">
													<a href="http://rd.BookingBuddy.com/?r=i1295096n${newsletter_id}&u=${tracking_code}&nltv=${nltv}">
														<img src="http://i.slimg.com/htmlemail/bb/ttd/BB_Logo.png" width="126"  height="18" alt="BookingBuddy" border="0" style="display:block; ">
													</a>
												</td>
											</tr>
										</tbody>
									</table>
									<!-- subject line -->
									<table border="0" align="right" valign="center" cellpadding="0" cellspacing="0" >
										<tbody>
											<tr>
												<td align="right" style="font-family: $font-family; font-size:16px; font-weight:bold; color:$color-boldblack;">
													Weekly Top Travel Deals
												</td>
											</tr>
										</tbody>
									</table>
									<!-- spacing -->
									<table width="5" height="1" border="0" align="right" cellpadding="0" cellspacing="0" style="width:5px;height:1px;">
										<tbody>
											<tr>
												<td width="5" height="1" style="font-size: 1px; line-height: 1px;">&nbsp;</td>
											</tr>
										</tbody>
									</table>
								</td>
							</tr>
							<!-- navigator -->
							<tr>
								<td width="100%" height="35" bgcolor=$color-blue>
									<table width="100%" cellspacing="0" cellpadding="0" border="0" align="center">
											<tr>
												<td style="padding-left:5px;" align="center"><a style="text-decoration:none; " href="http://rd.bookingbuddy.com/?r=i17748251n${newsletter_id}&u=${tracking_code}&nltv=${nltv}"><span style="text-decoration:none;font-size: 14px; font-family:$font-family; color:#ffffff;" >FLIGHTS</span></a></td>
												<td style="padding-left:10px;" align="center"><a style="text-decoration:none; " href="http://rd.bookingbuddy.com/?r=i17748260n${newsletter_id}&u=${tracking_code}&nltv=${nltv}"><span style="text-decoration:none;font-size: 14px; font-family:$font-family; color:#ffffff;">HOTELS</span></a></td>
												<td  nowrap="nowrap" style="padding-left:10px;" align="center"><a style="text-decoration:none; "  href="http://rd.bookingbuddy.com/?r=i17748264n${newsletter_id}&u=${tracking_code}&nltv=${nltv}"><span style="text-decoration:none;font-size: 14px; font-family:$font-family;color:#ffffff;">VACATION PACKAGES</span></a></td>
												<td style="padding-left:10px;" align="center"><a style="text-decoration:none; " href="http://rd.bookingbuddy.com/?r=i17748272n${newsletter_id}&u=${tracking_code}&nltv=${nltv}"><span style="text-decoration:none;font-size: 14px; font-family:$font-family;color:#ffffff;">CARS</span></a></td>
												<td style="padding-left:10px; " align="center"><a style="text-decoration:none; " href="http://rd.bookingbuddy.com/?r=i17748275n${newsletter_id}&u=${tracking_code}&nltv=${nltv}"><span style="text-decoration:none;font-size: 14px; font-family:$font-family; color:#ffffff;">CRUISES</span></a></td>
											</tr>

									</table>
								</td>
							</tr>
							<!-- Spacing -->
							<tr>
								<td width="100%" height="15" style="font-size: 1px; line-height: 15px;"></td>
							</tr>
							<!-- Module 1 -->
							#if ($feature_fare_depature_city != "" || $feature_story_url != "")
								<!-- title -->
								<tr>
									<td width="100%" height="30" bgcolor=$color-orange>
										<table width="100%" cellspacing="0" cellpadding="0" border="0" align="left">
											<tr>
												<td style="font-family:$font-family; font-size:16px; font-weight:bold; color:#ffffff;padding-left: 10px;">
													#if ($engaged == "true")
														Top Flight Deal of the Week
														
													#else
														What's Happening in Travel Now	
													#end
												</td>
											</tr>
										</table>
									</td>
								</tr>
								<!-- content -->
								#if ($engaged == "true")
									#feature_fare($feature_fare_depature_city, $feature_fare_arrival_city, $feature_fare_depature_airport_code, $feature_fare_arrival_airport_code, $feature_fare_price, $feature_fare_url, $feature_fare_image_url)
								#else
									#feature_story($feature_story_url,$feature_story_img_url,$feature_story_title,$feature_story_summary, $feature_story_img_alt)
								#end
								<!-- Horizontal Spacing -->
								<tr>
									<td width="100%" height="15" style="font-size: 1px; line-height: 15px;"></td>
								</tr>
							#end
							<!-- End of Module 1 -->
							<!-- Module 2 -->
							#if ($bbdndeal_destination_0 != "")
								<!-- title -->
								<tr>
									<td width="100%" height="30" >
										<table width="100%" cellspacing="0" cellpadding="0" border="0" align="left">
											<tr>
												<td style="font-family:$font-family; font-size:15px; font-weight:bold; color:#282828;">
													#if ($engaged == "true")
														Recommended for You
													#else
														Where to next
													#end
												</td>
											</tr>
										</table>
									</td>
								</tr>
								<!-- Content 1 -->
								#display_bbdndeal_1($bbdndeal_destination_0, $bbdndeal_type_0, $bbdndeal_title_0, $bbdndeal_source_0, $bbdndeal_price_0, $bbdndeal_url_0, $bbdndeal_imageurl_0, true)
								<!-- Vertical Spacing -->
								<tr>
									<td width="100%" height="10" style="font-size: 1px; line-height: 10px;"></td>
								</tr>
								#display_bbdndeal_1($bbdndeal_destination_1, $bbdndeal_type_1, $bbdndeal_title_1, $bbdndeal_source_1, $bbdndeal_price_1, $bbdndeal_url_1, $bbdndeal_imageurl_1, false)
								<!-- Vertical Spacing -->
								<tr>
									<td  width="100%" height="10" style="font-size: 1px; line-height: 10px;"></td>
								</tr>
								#display_bbdndeal_1($bbdndeal_destination_2, $bbdndeal_type_2, $bbdndeal_title_2, $bbdndeal_source_2, $bbdndeal_price_2, $bbdndeal_url_2,$bbdndeal_imageurl_2, false)
								<!-- Vertical Spacing -->
								<tr>
									<td width="100%" height="15" style="font-size: 1px; line-height: 15px;"></td>
								</tr>
							#end
							<!-- End of Module 2 -->
							<!-- Module 3 -->
							#if ($bbdndeal_destination_3 != "")
								<!-- title -->
								<tr>
									<td width="100%" height="30" >
										<table width="100%" cellspacing="0" cellpadding="0" border="0" align="left">
											<tr>
												<td style="font-family:$font-family; font-size:15px; font-weight:bold; color:#282828;">
													#if ($engaged == "true")
														BookingBuddy Top Picks
													#else
														Weekend Getaways
													#end
												</td>
											</tr>
										</table>
									<td>
								</tr>
								<!-- image banner -->
								<tr>
									<td width="480" height="80">
										<table width="480" cellspacing="0" cellpadding="0" border="0" align="left">
											<tr>
												<td align="center" width="480" height="80">
													<img src="http://i.slimg.com/htmlemail/bb/ttd/$hotel_module_img"  alt="image-banner"  width="480" height="80" border="0" style="display:block; ">
												</td>
											</tr>
										</table>
									</td>
								</tr>
								<!-- Vertical Spacing -->
								<tr>
									<td width="100%" height="5" style="font-size: 1px; line-height: 5px;"></td>
								</tr>
								<!-- Content 1 -->
								#display_bbdndeal_2($bbdndeal_destination_3, $bbdndeal_type_3, $bbdndeal_title_3, $bbdndeal_source_3, $bbdndeal_price_3, $bbdndeal_url_3)
								<!-- Vertical Spacing -->
								<tr>
									<td width="100%" height="5" style="font-size: 1px; line-height: 5px;"></td>
								</tr>
								<!-- Content 2 -->
								#display_bbdndeal_2($bbdndeal_destination_4, $bbdndeal_type_4, $bbdndeal_title_4, $bbdndeal_source_4, $bbdndeal_price_4, $bbdndeal_url_4)
								<!-- Vertical Spacing -->
								<tr>
									<td width="100%" height="5" style="font-size: 1px; line-height: 5px;"></td>
								</tr>
								<!-- Content 3 -->
								#display_bbdndeal_2($bbdndeal_destination_5, $bbdndeal_type_5, $bbdndeal_title_5, $bbdndeal_source_5, $bbdndeal_price_5, $bbdndeal_url_5)
								<!-- Vertical Spacing -->
								<tr>
									<td width="100%" height="15" style="font-size: 1px; line-height: 15px;"></td>
								</tr>
							#end
							<!-- End of Module 3 -->
							<!-- Module 4 -->
							#if ($bbdndeal_destination_6 != "")
								<!-- title -->
								<tr>
									<td width="100%" height="30" >
										<table width="100%" cellspacing="0" cellpadding="0" border="0" align="left">
											<tr>
												<td style="font-family:$font-family; font-size:15px; font-weight:bold; color:#282828;">
													Popular Deals
												</td>
											</tr>
										</table>
									<td>
								</tr>
								<!-- Vertical Spacing -->
								<tr>
									<td width="100%" height="5" style="font-size: 1px; line-height: 5px;"></td>
								</tr>
								<!-- Content 1 -->
								#display_bbdndeal_3($bbdndeal_destination_6, $bbdndeal_type_6, $bbdndeal_title_6, $bbdndeal_source_6, $bbdndeal_price_6, $bbdndeal_url_6)
								<!-- Vertical Spacing -->
								<tr>
									<td width="100%" height="5" style="font-size: 1px; line-height: 5px;"></td>
								</tr>
								<!-- Content 2 -->
								#display_bbdndeal_3($bbdndeal_destination_7, $bbdndeal_type_7, $bbdndeal_title_7, $bbdndeal_source_7, $bbdndeal_price_7, $bbdndeal_url_7)
								<!-- Vertical Spacing -->
								<tr>
									<td width="100%" height="5" style="font-size: 1px; line-height: 5px;"></td>
								</tr>
								<!-- Content 3 -->
								#display_bbdndeal_3($bbdndeal_destination_8, $bbdndeal_type_8, $bbdndeal_title_8, $bbdndeal_source_8, $bbdndeal_price_8, $bbdndeal_url_8)
								<!-- Vertical Spacing -->
								<tr>
									<td width="100%" height="15" style="font-size: 1px; line-height: 15px;"></td>
								</tr>
							#end
							<!-- End of Module 4 -->
							#if ($faredeal_arrival_city_0 != "")
								##when we don't even have the first fare, just collapse the whole module
								<!-- Module 5 -->
								<tr>
									<td width="100%" height="30" >
										<table width="100%" cellspacing="0" cellpadding="0" border="0" align="left">
											<tr>
												<td style="font-family:$font-family; font-size:15px; font-weight:bold; color:#282828;">
													Flights from ${dep_city_name_txt} (${dep_airport_code})
												</td>
											</tr>
										</table>
									<td>
								</tr>
								<!-- image banner -->
								<tr>
									<td width="480" height="65">
										<table width="480" cellspacing="0" cellpadding="0" border="0" align="left">
											<tr>
												<td align="center" width="480" height="65">
													<img src="http://i.slimg.com/htmlemail/bb/ttd/Flight_Module.jpg"  alt="image-banner-flight"  width="480" height="65" border="0" style="display:block; ">
												</td>
											</tr>
										</table>
									</td>
								</tr>
								#display_fare_deal($faredeal_arrival_city_0, $faredeal_arrival_airport_0, $faredeal_price_0, $faredeal_id_0, $faredeal_url_0, false)
								#display_fare_deal($faredeal_arrival_city_1, $faredeal_arrival_airport_1, $faredeal_price_1, $faredeal_id_1, $faredeal_url_1, true)
								#display_fare_deal($faredeal_arrival_city_2, $faredeal_arrival_airport_2, $faredeal_price_2, $faredeal_id_2, $faredeal_url_2, false)
								#display_fare_deal($faredeal_arrival_city_3, $faredeal_arrival_airport_3, $faredeal_price_3, $faredeal_id_3, $faredeal_url_3, true)
								#display_fare_deal($faredeal_arrival_city_4, $faredeal_arrival_airport_4, $faredeal_price_4, $faredeal_id_4, $faredeal_url_4, false)
								#display_fare_deal($faredeal_arrival_city_5, $faredeal_arrival_airport_5, $faredeal_price_5, $faredeal_id_5, $faredeal_url_5, true)
								#display_fare_deal($faredeal_arrival_city_6, $faredeal_arrival_airport_6, $faredeal_price_6, $faredeal_id_6, $faredeal_url_6, false)
								#display_fare_deal($faredeal_arrival_city_7, $faredeal_arrival_airport_7, $faredeal_price_7, $faredeal_id_7, $faredeal_url_7, true)
								<!-- see all fares -->
								<tr>
									<td width="480" height="35" bgcolor=$color-white style="border-top:$border-top;" align="right">
										<a href="http://rd.bookingbuddy.com/?r=i7416122n${newsletter_id}&u=${tracking_code}&departure_city=${dep_airport_code}&nltv=${nltv}" target="_blank" style="text-decoration:none; ">
											<span style="text-decoration:none; font-family:$font-family; font-size:12px;color:#1656a5;">See all ${dep_city_name_txt} Flight Deals &#x25B8;</span>										
										</a>	
									</td>
								</tr>
							#end
							<!-- widget -->
							<tr>
								<td width="480" height="187" bgcolor=$color-white style="border:none;" align="center">
									<a href="http://rd.bookingbuddy.com/?r=i17748039n${newsletter_id}&u=${tracking_code}&search_mode=vacation&pt=1&arrival_city=$bbdndeal_destination_0&nltv=${nltv}" target="_blank" style="text-decoration:none; ">
										<img width="480" height="187" src="http://i.slimg.com/sc/bk/graphic/w/wi/widget_updated.png" alt="" border="0">										
									</a>

								</td>
							</tr>
							<!-- Vertical Spacing -->
							<tr>
								<td width="100%" height="10" style="font-size: 1px; line-height: 10px;"></td>
							</tr>
							<!-- Advertise -->
							<tr>
								<td>
									<table align="center" width="480">
										<tr>
											<td align="center">
												<div style="padding:8px 0;">
													<a href="http://ad.doubleclick.net/jump/ta.bb.com.email/bb_top_travel_deals;dcove=r;sz=180x150;nid=${newsletter_id};${dart_tags}${dart_origin_tags}${dart_destination_tags};tile=1;ord=${dart_ord}?"><img src="http://ad.doubleclick.net/ad/ta.bb.com.email/bb_top_travel_deals;dcove=r;sz=180x150;nid=${newsletter_id};${dart_tags}${dart_origin_tags}${dart_destination_tags};tile=1;ord=${dart_ord}?" alt="" border="0" /></a>
												</div>
											</td>
											<td align="center">
												<div style="padding:8px 0;">
													<a href="http://ad.doubleclick.net/jump/ta.bb.com.email/bb_top_travel_deals;dcove=r;sz=180x150;nid=${newsletter_id};${dart_tags}${dart_origin_tags}${dart_destination_tags};tile=3;ord=${dart_ord}?"><img src="http://ad.doubleclick.net/ad/ta.bb.com.email/bb_top_travel_deals;dcove=r;sz=180x150;nid=${newsletter_id};${dart_tags}${dart_origin_tags}${dart_destination_tags};tile=3;ord=${dart_ord}?" alt="" border="0" /></a>
												</div>
											</td>
										</tr>
									</table>
								</td>
							</tr>
							<!-- footer -->
							<tr>
								<td width="480" height="25px" bgcolor=$color-blue>
									<table width="100%" cellspacing="0" cellpadding="0" border="0" align="center">
											<tr>
												<td style="padding-left:5px;" align="center"><a style="text-decoration:none; " href="http://rd.bookingbuddy.com/?r=i17748812n${newsletter_id}&u=${tracking_code}&nltv=${nltv}&email=${email_encoded}&mode=prefs${source}"><span style="text-decoration:none; font-family:$font-family;font-size:12px; color:#ffffff;">Update Preferences</span></a></td>
												<td bgcolor="#1a67b2" class="nav"><img src="http://i.slimg.com/bookingbuddy/nl/blue_nav/dots.gif" alt="" border="0" border="0" style="display:block; "></td>
												<td style="padding-left:10px;"  align="center"><a style="text-decoration:none; " href="http://rd.bookingbuddy.com/?r=i17748812n${newsletter_id}&u=${tracking_code}&nltv=${nltv}&email=${email_encoded}&mode=prefs${source}"><span style="text-decoration:none; font-family:$font-family;font-size:12px; color:#ffffff;">Unsubscribe</span></a></td>
												<td bgcolor="#1a67b2" class="nav"><img src="http://i.slimg.com/bookingbuddy/nl/blue_nav/dots.gif" alt="" border="0"  style="display:block; "></td>
												<td  nowrap="nowrap" style="padding-left:10px;" align="center"><a style="text-decoration:none; " href="http://rd.bookingbuddy.com/?r=i17748854n${newsletter_id}&u=${tracking_code}&nltv=${nltv}${source}" ><span style="text-decoration:none; font-family:$font-family;font-size:12px; color:#ffffff;">Term of Use</span></a></td>
												<td bgcolor="#1a67b2" class="nav"><img src="http://i.slimg.com/bookingbuddy/nl/blue_nav/dots.gif" alt="" border="0"  style="display:block; "></td>
												<td style="padding-left:10px;" align="center"><a style="text-decoration:none; " href="http://rd.bookingbuddy.com/?r=i17748861n${newsletter_id}&u=${tracking_code}&nltv=${nltv}${source}"><span style="text-decoration:none; font-family:$font-family;font-size:12px; color:#ffffff;">Privacy Policy</span></a></td>
												<td bgcolor="#1a67b2" class="nav"><img src="http://i.slimg.com/bookingbuddy/nl/blue_nav/dots.gif" alt="" border="0" style="display:block; "></td>
												<td style="padding-left:10px; " align="center"><a style="text-decoration:none; " href="http://rd.bookingbuddy.com/?r=i17748874n${newsletter_id}&u=${tracking_code}&nltv=${nltv}${source}" ><span style="text-decoration:none; font-family:$font-family;font-size:12px; color:#ffffff;">Feedback</span></a></td>
											</tr>
									</table>
								</td>
							</tr>
							<!-- some words -->
							<tr>
								<td width="480" bgcolor="#f6f6f6">
									 <table  width="480" border="0" cellspacing="0" cellpadding="0" align="center">
										<tr>
										  <td class="fineprint">
											<span class="ftrtext">
											<p style="font-size: 10px; font-family:$font-family; color: $color-boldblack;">
												You received this email because you subscribed as: ${email_address}
												.This is a commercial newsletter that contains advertisements from
												travel suppliers and agencies. If you no longer wish to receive this
												newsletter, please <a style="text-decoration:none; " href="http://rd.bookingbuddy.com/?r=i17748812n${newsletter_id}&u=${tracking_code}&nltv=${nltv}&email=${email_encoded}&mode=prefs${source}" ><span style="color: $color-boldblack;text-decoration: none;"><u>unsubscribe here</u></span></a>.
											</p>
											<p style="font-size: 10px;font-family:$font-family; color: $color-boldblack;">
											BookingBuddy.com is a travel search service and information provider. We
											do not sell travel products or services. We help you search for travel
											products/services from third-party. However, the <span style="font-size: 8px;">3<sup style="font-size: 6px;">rd</sup></span> party suppliers
											that supply travel products and services may change the offers for variety of reasons,
											and we cannot therefore guarantee any information in their offers, which change from time to time.
											We are not responsible for <span style="font-size: 8px;">3<sup style="font-size: 6px;">rd</sup></span> party products, services or site content
											</p>
											<p style="font-size: 10px; font-family:$font-family;color: $color-boldblack;">
											Copyright &copy; 2005-${current_year} Smarter Travel Media LLC. All Rights
											Reserved. BookingBuddy is a trademark of BookingBuddy.com, Inc., a
											wholly-owned subsidiary of Smarter Travel Media LLC.
											</p>
											<p style="font-size: 10px;font-family:$font-family; color: $color-boldblack;">
											<a href="http://www.smartertravelmedia.com" style="text-decoration:none;color: $color-boldblack;"><span style="text-decoration:none;"><u>Smarter Travel Media LLC</u></span></a> | 226 Causeway Street | 3rd Floor | Boston, MA 02114 | 617.886.5555
											</p>
											</span>
										  </td>
										</tr>
	  								</table>
								</td>
							</tr>
						</tbody>
					</table>
				</td>
			</tbody>
		</table>
	</body>
</html>